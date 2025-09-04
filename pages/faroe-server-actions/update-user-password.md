---
title: "Update user password"
---

# Update user password

## Overview

Here's how the process looks for the user:

1. The user starts the process.
2. The user verifies their identity with their current password.
3. The user enters their new password.
4. The process is completed and the user's password is updated.

## Start password update

Create a new [user password update](/concepts/user-password-resets) with the [`create_user_password_update`](/references/faroe-server-actions/actions/create_user_password_update) action. Store the returned token.

```
user_password_update, user_password_update_token = create_user_password_update(
    session_token
)
```

## Verify user identity

Verify the user's identity with their password using the [`verify_user_password_update_user_password`](/references/faroe-server-actions/actions/verify_user_password_update_user_password) action.

```
verify_user_password_update_user_password(
    session_token,
    user_password_update_token,
    password
)
```

## Set new password

Set the user's new password with the [`set_user_password_update_new_password`](/references/faroe-server-actions/actions/set_user_password_update_new_password) action. This can only be done once.

```
set_user_password_update_new_password(
    session_token,
    user_password_update_token,
    password
)
```

## Complete password update

Complete the user password update with the [`complete_user_password_update`](/references/faroe-server-actions/actions/complete_user_password_update) action.

**Existing user sessions will not be invalidated.**

```
complete_user_password_update(
    session_token,
    user_password_update_token
)
```
