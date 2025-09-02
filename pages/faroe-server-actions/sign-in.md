---
title: "Sign in"
---

# Sign in

## Overview

Here's how the process looks for the user:

1. The user enters their email address.
2. The user enters their password.
3. The sign-in is completed and a new session is issued.

## Start sign-in

Use the [`create_signin`]() action to create a new [signin]() with the user's email address. Store the returned signin token.

```
signin, signin_token = create_signin(
    email_address
)
```

## Verify user first factor

Use the [`verify_signin_user_password`]() action to verify the user's first factor with their password.

```
verify_signin_user_password(
    signin_token,
    password
)
```

## Complete sign-in

Complete the sign-in by exchanging the signin for a new session with the [`complete_signin()`] action.

```
session, session_token = complete_signin(
    signin_token
)
```
