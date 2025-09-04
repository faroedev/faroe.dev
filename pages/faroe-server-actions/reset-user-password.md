---
title: "Reset user password"
---

# Reset user password

## Overview

Here's how the process looks for the user:

1. The user enters their email address.
2. A temporary password is sent to the user's inbox.
3. The user enters the temporary password.
4. The user enters their new password.
3. The process is completed and the user's password is reset.

## Start password reset

Use the [`create_user_password_reset`](/references/faroe-server-actions/actions/create_user_password_reset) action to create a new [user password reset](/concepts/user-password-resets) with the user's email address. Store the returned token.

```
user_password_reset, user_password_reset_token = create_user_password_reset(
    email_address
)
```

## Verify user first factor

Use the [`verify_user_password_reset_temporary_password`](/references/faroe-server-actions/actions/verify_user_password_reset_temporary_password) action to verify the user's first factor with the temporary password.

```
verify_user_password_reset_temporary_password(
    user_password_reset_token,
    temporary_password
)
```

## Set new password

Set the user's new password with the [`set_user_password_reset_new_password`](/references/faroe-server-actions/actions/set_user_password_reset_new_password) action. This can only be done once.

```
set_user_password_reset_new_password(
    user_password_reset_token,
    password
)
```

## Complete password reset

Complete the user password reset with the [`complete_user_password_reset`](/references/faroe-server-actions/actions/complete_user_password_reset) action. This will also attempt to issue a new [session](/concepts/sessions).

**Existing user sessions will not be invalidated.**

```
complete_user_password_reset(
    session_token,
    user_password_reset_token
)
```
