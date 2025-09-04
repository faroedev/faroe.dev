---
title: "Sign up"
---

# Sign up

## Overview

Here's how the process looks for the user:

1. The user enters their email address.
2. A verification code is sent to the email address.
3. The user enters the verification code.
4. The user sets their password.
5. The sign-up is completed and a new session is issued.

## Start sign-up

Use the [`create_signup`](/references/faroe-server-actions/actions/create_signup) action to create a new [signup](/concepts/signups). This action also sends an email address verification code to the user's inbox. Store the returned signup token.

Email addresses are considered case-sensitive. Faroe does not prevent users from using "tricks" that allow users to use the same "base" email address to create multiple accounts (e.g. using `+` or `.` in Google account email addresses).

```
signup, signup_token = create_signup(
    email_address
)
```

## Resend email address verification code

Use the [`send_signup_email_address_verification_code`](/references/faroe-server-actions/actions/send_signup_email_address_verification_code) action to send the verification code to the user's inbox again.

```
send_signup_email_address_verification_code(
    signup_token
)
```

## Verify email address

Prompt the user for the verification code and verify it using the [`verify_signup_email_address_verification_code`](/references/faroe-server-actions/actions/verify_signup_email_address_verification_code) action.

```
verify_signup_email_address_verification_code(
    signup_token,
    email_address_verification_code
)
```

## Set password

Set the password with the [`set_signup_password`](/references/faroe-server-actions/actions/set_signup_password) action. The password must be between 10 and 100 characters.

The password can only be set once.

```
set_signup_password(
    signup_token,
    password
)
```

## Complete sign-up

Complete the sign-up by creating a new user with the [`complete_signup`](/references/faroe-server-actions/actions/complete_signup) action. This action will also attempt to issue a new [session](/concepts/sessions).

```
session, session_token = complete_signup(
    signup_token
)
```
