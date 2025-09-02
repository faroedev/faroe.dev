---
title: "verify_user_email_address_update_user_password action"
---

# verify_user_email_address_update_user_password action

Verify a user email address update user password and set it as user identity verified.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_email_address_update_token` (string)
-   `password` (string)

## Return values

None.

## Error codes

-   `email_address_not_verified`
-   `incorrect_password`
-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_email_address_update_token`
-   `rate_limited`
-   `session_mismatch`
-   `user_identity_already_verified`

## Example

```
get_user_email_address_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_email_address_update_token: "2c3sagxfknrjn5u6q587m3wf.yr9knqccb4y6wqjws6pquc22",
    password: "SuperSecretPassword"
)
```
