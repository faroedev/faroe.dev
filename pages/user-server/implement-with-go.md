---
title: "Implement user server with Go"
---

# Implement user server with Go

We provide an official package to make it easier to build user servers with Go.

See the package [API reference](https://pkg.go.dev/github.com/faroedev/go-user-server) for details.

```
go get github.com/faroedev/go-faroe-user-server
```

Implement the [`ActionsInterface`](https://pkg.go.dev/github.com/faroedev/go-user-server#ActionsInterface) interface.

```go
type ActionsInterface interface {
	CreateUserAction(actionInvocationId string, emailAddress string, passwordHash []byte, passwordHashAlgorithmId string, passwordSalt []byte) (UserStruct, error)
	GetUserAction(actionInvocationId string, userId string) (UserStruct, error)
	GetUserByEmailAddressAction(actionInvocationId string, emailAddress string) (UserStruct, error)
	UpdateUserEmailAddressAction(actionInvocationId string, userId string, emailAddress string, userEmailAddressCounter int32) error
	UpdateUserPasswordHashAction(actionInvocationId string, userId string, passwordHash []byte, passwordHashAlgorithmId string, passwordSalt []byte, userPasswordHashCounter int32) error
	IncrementUserSessionsCounterAction(actionInvocationId string, userId string, userSessionsCounter int32) error
	DeleteUserAction(actionInvocationId string, userId string) error
}
```

Then, create a new [`ServerStruct`](https://pkg.go.dev/github.com/faroedev/go-user-server#ServerStruct) with [`NewServer()`](https://pkg.go.dev/github.com/faroedev/go-user-server#NewServer). 

Use the [`ServerStruct.ResolveActionInvocationEndpointRequest()`](https://pkg.go.dev/github.com/faroedev/go-user-server#ServerStruct.ResolveActionInvocationEndpointRequest) to create an action invocation endpoint. It takes a request body of an action invocation request and returns the response body. It will return an `error` if the request is invalid.

**The action invocation endpoint should be protected and only accessible to trusted clients.** Some options are private networks and request signing.

```go
import "github.com/faroedev/go-faroe-user-server"

var server = userserver.NewServer(actions)

func handleRequest(w http.ResponseWriter, r *http.Request) {
    // TODO: Protect route.

    bodyJSONBytes, err := io.ReadAll(r.Body)
    if err != nil {
        w.WriteHeader(http.StatusBadRequest)
        return
    }

    resultJSON, err := server.ResolveActionInvocationEndpointRequest(string(bodyJSONBytes))
    if err != nil {
        w.WriteHeader(http.StatusBadRequest)
        return
    }

    w.Header().Set("Content-Type", "application/json")
    w.Write([]byte(resultJSON))
}
```
