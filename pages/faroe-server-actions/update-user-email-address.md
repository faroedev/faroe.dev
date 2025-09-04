---
title: "Update user email address"
---

# Update user email address

## Overview

Here's how the process looks for the user:

1. The user enters their new email address.
2. A verification code is sent to the new email address.
3. The user enters the verification code.
4. The user verifies their identity with their password.
5. The process is completed and the user's email address is updated.

## Start email address update

Create a new [user email address update](/concepts/user-email-address-updates) with the [`create_user_email_address_update`](/references/faroe-server-actions/actions/create_user_email_address_update) action. A verification code will be sent to the new email address. Store the returned token.

```
user_email_address_update, user_email_address_update_token = create_user_email_address_update(
    session_token,
    new_email_address
)
```

## Resend email address verification code

Use the [`send_user_email_address_update_email_address_verification_code`](/references/faroe-server-actions/actions/send_user_email_address_update_email_address_verification_code) action to resend the verification code.

```
send_user_email_address_update_email_address_verification_code(
    session_token,
    user_email_address_update_token
)
```

## Verify email address verification code

Prompt the user for the verification code and use the [`verify_user_email_address_update_email_address_verification_code`](/references/faroe-server-actions/actions/verify_user_email_address_update_email_address_verification_code) action to verify it.

```
verify_user_email_address_update_email_address_verification_code(
    session_token,
    user_email_address_update_token,
    email_address_verification_code
)
```

## Verify user identity

Verify the user's identity with their password using the [`verify_user_email_address_update_user_password`](/references/faroe-server-actions/actions/verify_user_email_address_update_user_password) action.

```
verify_user_email_address_update_user_password(
    session_token,
    user_email_address_update_token,
    password
)
```

## Complete email address update

Complete the user email address update with the [`complete_user_email_address_update`](/references/faroe-server-actions/actions/complete_user_email_address_update) action.

```
complete_user_email_address_update(
    session_token,
    user_email_address_update_token
)
```