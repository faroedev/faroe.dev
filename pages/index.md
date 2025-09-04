---
title: "Faroe"
---

# Faroe

*This software is in active development and has only gone through minimal testing.*

Faroe is an open source auth server packaged as a Go library.

Some key features of the server:

1. Takes care of all the hard parts. Passwords, email address verification, sessions, rate limiting, password resets, and more.
2. Extends your existing user database instead of replacing it. Full customizability and no more data synchronization.
3. No direct connections to your database. Just basic HTTP requests.
4. Only ephemeral data is stored. Less things to manage and worry about.

```ts
const result = await client.createSignup(emailAddress);
if (!result.ok) {
    console.log(result.errorCode);
    return;
}
console.log(result.signup);
window.localStorage.setItem("signup_token", result.signupToken);
```

The package itself is also very flexible. The storage layer is fully customizable and can run in any environment. The only thing you need to bring is an email server.

```go
actions := faroe.NewActions(
    mainStorage,
    cache,
    rateLimitStorage,
    logger,
    userPasswordHashAlgorithms,
    temporaryPasswordHashAlgorithm,
    cpuCount,
    faroe.RealClock,
    faroe.AllowAllEmailAddresses,
    emailSender,
    userActionInvocationEndpointClient,
    sessionConfig
)
```

Only password authentication is supported. Support for passkeys and 2FA are planned but there are no immediate plans to add social login (e.g. Sign in with Google). 

Read the [Overview](/faroe-server/overview) page to learn more and get started.