---
title: "Set up a Faroe server"
---

# Set up a Faroe server

A Faroe server is a server that exposes an [action invocation endpoint](/references/action-invocation-endpoint) for Faroe server [actions](/concepts/actions).

This may take up to an hour depending on how comfortable you are with the language and architecture. If you want to evaluate the server first, consider using the prebuilt local server by following the [Quick-start guide](/faroe-server/quickstart-guide).

_All implementations of interfaces must be thread-safe unless specified otherwise._

## Storage

The first step is to define you storage.

It is a key-value store that implements [`StorageInterface`](https://pkg.go.dev/github.com/faroedev/faroe#StorageInterface). It should be strongly consistent. Any writes/updates should be immediately visible to all subsequent reads. Beyond this consistency guarantee, there are no other requirements. You may use a traditional persistent database with backups or use a temporary storage like an in-memory store.

The entry value, counter, and optionally the expiration timestamp should be stored under each key. The counter is used to prevent race conditions. The expiration is just a hint. You may delete entries past its expiration to free up storage.

```go
type StorageInterface interface {
	Get(key string) ([]byte, int32, error)
	Add(key string, value []byte, expiresAt time.Time) error
	Update(key string, value []byte, expiresAt time.Time, counter int32) error
	Delete(key string) error
}
```

Example implementations are available:

- [MySQL with `database/sql`](https://code.faroe.dev/faroe-storage-sql-mysql)
- [PostgreSQL with `database/sql`](https://code.faroe.dev/faroe-storage-sql-postgresql)
- [SQLite with `database/sql`](https://code.faroe.dev/faroe-storage-sql-sqlite)
- [Go maps](https://code.faroe.dev/faroe-storage-map)

## User store

Create a user store that implements an [`UserStoreInterface`](https://pkg.go.dev/github.com/faroedev/faroe#UserStoreInterface). This allows Faroe to interact with your existing user data.

```go
type UserStoreInterface interface {
	CreateUser(emailAddress string, passwordHash []byte, passwordHashAlgorithmId string, passwordSalt []byte) (UserStruct, error)
	GetUser(userId string) (UserStruct, error)
	GetUserByEmailAddress(emailAddress string) (UserStruct, error)
	UpdateUserEmailAddress(userId string, emailAddress string, userEmailAddressCounter int32) error
	UpdateUserPasswordHash(userId string, passwordHash []byte, passwordHashAlgorithmId string, passwordSalt []byte, userPasswordHashCounter int32) error
	IncrementUserSessionsCounter(userId string, userSessionsCounter int32) error
	DeleteUser(userId string) error
}
```

Example implementations are available:

- [MySQL with `database/sql`](https://code.faroe.dev/faroe-user-store-sql-mysql)
- [PostgreSQL with `database/sql`](https://code.faroe.dev/faroe-user-store-sql-postgresql)
- [SQLite with `database/sql`](https://code.faroe.dev/faroe-user-store-sql-sqlite)

Alternatively, you may create a separate [user server](/user-server/overview) to handle database operations for your users in a dedicated server. To connect to your user server, use  [`NewUserServerClient()`](https://pkg.go.dev/github.com/faroedev/faroe#NewUserServerClient) to create [`UserServerStruct`](https://pkg.go.dev/github.com/faroedev/faroe#UserServerStruct), which implements `UserStoreInterface`. `NewUserServerClient()` takes an [`ActionInvocationEndpointClientInterface`](https://pkg.go.dev/github.com/faroedev/faroe#ActionInvocationEndpointClientInterface), which is used to send action invocation requests to the user server's action invocation endpoint.

```go
userStore := faroe.NewUserServerClient(actionInvocationEndpointClient)
```

```go
type ActionInvocationEndpointClientInterface interface {
	SendActionInvocationEndpointRequest(body string) (string, error)
}
```

Because Faroe doesn't prescribe the authentication method used for action invocation endpoints, this is where you implement whatever authentication mechanism your user action endpoint uses.

## User password hash algorithm

The user password hash algorithm implements [`PasswordHashAlgorithmInterface`](https://pkg.go.dev/github.com/faroedev/faroe#PasswordHashAlgorithmInterface). The ID is a unique identifier for the algorithm. We recommend including the parameters alongside the algorithm name like `argon2id.65536.3.1.32`.

We recommend using Argon2id with 64MiB of memory, 3 iterations, and 1 degree of parallelism. An [example implementation for Argon2id](https://code.faroe.dev/faroe-password-hash-algorithm-argon2) is available.

```go
type PasswordHashAlgorithmInterface interface {
	Id() string
	SaltSize() int
	Hash(secret string, salt []byte) ([]byte, error)
}
```

## User password reset temporary password hashing

The user password reset temporary password hash algorithm also implements [`PasswordHashAlgorithmInterface`](https://pkg.go.dev/github.com/faroedev/faroe#PasswordHashAlgorithmInterface).

Temporary passwords used in user password resets are generated by the server. Because they are much stronger than user-defined passwords, you may use a weaker hashing algorithm than for user passwords. That said, you should still treat them as passwords and use hashing algorithms intended for passwords. We recommend Argon2id with 16MiB of memory, 3 iterations, and 1 degree of parallelism.

## Action error logger

The `LogActionError()` method of [`ActionErrorLoggerInterface`](https://pkg.go.dev/github.com/faroedev/faroe#ActionErrorLoggerInterface) will be used to log all internal errors.

```go
type ActionErrorLoggerInterface interface {
	LogActionError(timestamp time.Time, message string, actionInvocationId string, action string)
}
```

## Email sender

The email sender is an implementation of [`EmailSenderInterface`](https://pkg.go.dev/github.com/faroedev/faroe#EmailSenderInterface).

```go
type EmailSenderInterface interface {
	SendSignupEmailAddressVerificationCode(emailAddress string, emailAddressVerificationCode string) error
	SendUserEmailAddressUpdateEmailVerificationCode(emailAddress string, displayName string, emailAddressVerificationCode string) error
	SendUserPasswordResetTemporaryPassword(emailAddress string, displayName string, temporaryPassword string) error
	SendUserSignedInNotification(emailAddress string, displayName string, timestamp time.Time) error
	SendUserPasswordUpdatedNotification(emailAddress string, displayName string, timestamp time.Time) error
	SendUserEmailAddressUpdatedNotification(emailAddress string, displayName string, newEmailAddress string, timestamp time.Time) error
}
```

## Storage namespace

Storage entry keys are not globally namespaced. For example, an entry in the rate limit storage can have a same key as an entry in the cache. If you use a shared storage, make sure to prefix the key with `NAME.` (note the period) like `main.` and `rate_limit.`.

## Create server

Create a new [`ServerStruct`](https://pkg.go.dev/github.com/faroedev/faroe#ServerStruct) with [`NewServer()`](https://pkg.go.dev/github.com/faroedev/faroe#NewServer).

You can provide multiple user password hashing algorithms if your users use different algorithms. The first one will be used for hashing new passwords.

`maxConcurrentPasswordHashingProcesses` is the number of maximum CPU threads you want to dedicate to hashing passwords (user passwords and temporary passwords). Password hashing is expensive and will block the thread for the duration of the process.

```go
server := faroe.NewServer(
	storage,
	userStore,
	errorLogger,
	[]faroe.PasswordHashAlgorithmInterface{userPasswordHashAlgorithm},
	temporaryPasswordHashAlgorithm,
	maxConcurrentPasswordHashingProcesses,
	faroe.RealClock,
	faroe.AllowAllEmailAddresses,
	emailSender,
	faroe.SessionConfigStruct{
		InactivityTimeout:     30 * 24 * time.Hour,
		ActivityCheckInterval: time.Minute,
		CacheExpiration:       time.Minute,
	},
)
```

Handle action invocation endpoint requests with [`ServerStruct.ResolveActionInvocationEndpointRequestWithBlocklist()`](https://pkg.go.dev/github.com/faroedev/faroe#ServerStruct.ResolveActionInvocationEndpointRequestWithBlocklist). It takes an action invocation endpoint request body and returns the response body.

```go
import (
    "io"
	"net/http"

    "github.com/faroedev/faroe"
)

func handleRequest(w http.ResponseWriter, r *http.Request) {
    bodyBytes, err := io.ReadAll(r.Body)
	if err != nil {
		w.WriteHeader(http.StatusBadRequest)
		return
	}

	resultJSON, err := server.ResolveActionInvocationEndpointRequestWithBlocklist(string(bodyBytes), nil)
	if err != nil {
		w.WriteHeader(http.StatusBadRequest)
		return
	}

	w.Header().Set("Content-Type", "application/json")
	w.Write([]byte(resultJSON))
	return
}
```
