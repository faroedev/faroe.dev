---
title: "send_user_email_address_update_email_address_verification_code action"
---

# send_user_email_address_update_email_address_verification_code action

Send a user email address update's new email address verification code to the user email address update's email address.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_email_address_update_token` (string): A user email address update linked to the session.

## Return values

None.

## Error codes

-   `email_address_already_verified`
-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_email_address_update_token`
-   `rate_limited`
-   `session_mismatch`

## Example

```
send_user_email_address_update_email_address_verification_code(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_email_address_update_token: "2c3sagxfknrjn5u6q587m3wf.yr9knqccb4y6wqjws6pquc22"
)
```
