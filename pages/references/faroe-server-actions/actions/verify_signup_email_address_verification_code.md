---
title: "verify_signup_email_address_verification_code action"
---

# verify_signup_email_address_verification_code action

Verify a signup's email address verification code and set the signup's email address as verified.

## Parameters

-   `action_invocation_id` (string)
-   `signup_token` (string)
-   `email_address_verification_code`

## Error codes

-   `email_address_already_verified`
-   `incorrect_email_address_verification_code`
-   `internal_conflict`
-   `internal_error`
-   `invalid_signup_token`
-   `rate_limited`

## Example

```
verify_signup_email_address_verification_code(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signup_token: "yjickd8enm8n5kitm86233yt.egewfuvjna78sxpmq4kv8zfn",
    email_address_verification_code: "EH24M8YL"
)
```
