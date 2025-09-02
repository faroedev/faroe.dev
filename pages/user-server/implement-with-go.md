---
title: "Implement user server with Go"
---

# Implement user server with Go

We provide an official package to make it easier to build user servers with Go.

```
go get github.com/faroedev/go-faroe-user-server
```

Implement the [`ActionsInterface`]() interface.

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

Then, create a new [`ActionInvocationRequestResolverStruct`]() instance and create an [action invocation endpoint]().

`ActionInvocationRequestResolver.ResolveRequest()` takes a request body of an action invocation request and returns the response body. It will return an `error` if the request is invalid.

```go
import "github.com/faroedev/go-faroe-user-server"

var resolver = userserver.NewActionInvocationRequestResolver(actions)

func handleRequest(w http.ResponseWriter, r *http.Request) {
    bodyJSONBytes, err := io.ReadAll(r.Body)
    if err != nil {
        w.WriteHeader(http.StatusBadRequest)
        return
    }

    resultJSON, err := resolver.ResolveRequest(string(bodyJSONBytes))
    if err != nil {
        w.WriteHeader(http.StatusBadRequest)
        return
    }

    w.Write([]byte(resultJSON))
}
```
