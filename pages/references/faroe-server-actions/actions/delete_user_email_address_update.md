---
title: "delete_user_email_address_update action"
---

# delete_user_email_address_update action

Delete a user email address update.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_email_address_update_token` (string): A user email address update linked to the session.

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_email_address_update_token`
-   `session_mismatch`

## Example

```
delete_user_email_address_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_email_address_update_token: "2c3sagxfknrjn5u6q587m3wf.yr9knqccb4y6wqjws6pquc22"
)
```
