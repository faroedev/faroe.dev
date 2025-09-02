---
title: "set_signup_password action"
---

# set_signup_password action

Set a signup's password.

## Parameters

-   `action_invocation_id` (string)
-   `signup_token` (string)
-   `password` (string): Between 10 and 100 characters.

## Error codes

-   `email_address_not_verified`
-   `internal_conflict`
-   `internal_error`
-   `invalid_password_length`
-   `invalid_signup_token`
-   `password_already_set`
-   `weak_password`

## Example

```
set_signup_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signup_token: "yjickd8enm8n5kitm86233yt.egewfuvjna78sxpmq4kv8zfn",
    password: "SuperSecretPassword"
)
```
