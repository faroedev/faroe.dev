---
title: "verify_user_email_address_update_email_address_verification_code action"
---

# verify_user_email_address_update_email_address_verification_code action

Verify a user email address update's new email address verification code and set it as new email address verified.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_email_address_update_token` (string)
-   `email_address_verification_code` (string)

## Return values

None.

## Error codes

-   `email_address_already_verified`
-   `incorrect_email_address_verification_code`
-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_email_address_update_token`
-   `rate_limited`
-   `session_mismatch`

## Example

```
get_user_email_address_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_email_address_update_token: "2c3sagxfknrjn5u6q587m3wf.yr9knqccb4y6wqjws6pquc22",
    email_address_verification_code: "MYPLKYGP"
)
```
