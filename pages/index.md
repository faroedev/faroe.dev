---
title: "Faroe"
---

# Faroe

*This software is in active development and has only gone through minimal testing.*

Faroe is an open source auth server packaged as a Go library.

Some key features of the server:

1. Takes care of many auth components, including password verification, email address verification, session management, and rate limiting.
2. Extends your existing user database instead of replacing it.
3. Only ephemeral data is stored. Less things to manage and worry about.
4. No cookies. It works with both web and mobile applications.

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

```
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

Some limitations and downsides:

1. Users are identified with their email address. Username-only sign-in is not supported.
2. Only password authentication is supported. Passkey support is planned. We have no immediate plans to support social logins.

Read the [Overview]() page to get started.