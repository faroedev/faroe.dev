---
title: "send_signup_email_address_verification_code action"
---

# send_signup_email_address_verification_code action

Send a signup's email address verification code to the email address.

## Parameters

-   `action_invocation_id` (string)
-   `signup_token` (string)

## Error codes

-   `email_address_already_verified`
-   `internal_conflict`
-   `internal_error`
-   `invalid_signup_token`
-   `rate_limited`

## Example

```
send_signup_email_address_verification_code(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signup_token: "yjickd8enm8n5kitm86233yt.egewfuvjna78sxpmq4kv8zfn"
)
```
