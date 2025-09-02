---
title: "create_user_password_update action"
---

# create_user_password_update action

Create a new user password update linked to the session.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)

## Return values

-   `user_password_update` ([user_password_update](/references/faroe-server-actions/models/user_password_update))
-   `user_password_update_token` (string)

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`

## Example

```
create_user_password_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7"
)
```
