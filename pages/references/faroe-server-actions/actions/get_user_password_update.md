---
title: "get_user_password_update action"
---

# get_user_password_update action

Get a user password update.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_password_update_token` (string): A user password update linked to the session.

## Return values

-   `user_password_update` ([user_password_update](/references/faroe-server-actions/models/user_password_update))

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_password_update_token`
-   `invalid_session_token`
-   `session_mismatch`

## Example

```
get_user_password_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_password_update_token: "spjdfixngqtpu7y3ib22i34r.yc9gjp28k6v835vpf56uzfrf"
)
```
