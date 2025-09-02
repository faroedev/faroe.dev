---
title: "complete_user_email_address_update action"
---

# complete_user_email_address_update action

Update a user's email address. The user email address update must be set as new email address verified and user identity verified.

Existing user email address updates are invalidated. Existing sessions are not invalidated.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_email_address_update_token` (string)

## Return values

None.

## Error codes

-   `email_address_not_verified`
-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_email_address_update_token`
-   `session_mismatch`
-   `user_identity_not_verified`

## Example

```
complete_user_email_address_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_email_address_update_token: "2c3sagxfknrjn5u6q587m3wf.yr9knqccb4y6wqjws6pquc22"
)
```
