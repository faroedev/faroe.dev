---
title: "Delete user"
---

# Delete user

## Overview

Here's how the process looks for the user:

1. The user starts the process.
2. The user enters their password.
3. The process completed and the user is deleted.

## Start user deletion

Create a new [user deletion]() with the [`create_user_deletion`]() action. Store the returned token.

```
user_deletion, user_deletion_token = create_user_deletion(
    session_token
)
```

## Verify user identity

Verify the user's identity with their password using the [`verify_user_deletion_user_password`]() action.

```
verify_user_deletion_user_password(
    session_token,
    user_deletion_token,
    password
)
```

## Complete user deletion

Complete the user deletion with the [`complete_user_deletion`]() action.

```
complete_user_deletion(
    session_token,
    user_deletion_token
)
```
