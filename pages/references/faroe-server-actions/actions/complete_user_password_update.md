---
title: "complete_user_password_update action"
---

# complete_user_password_update action

Update a user's password and issues a new session. The user password update must be set as user identity verified.

Existing signins, user email address updates, user password updates, user deletion, and user password resets are invalidated. **Existing sessions are not invalidated.**

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_password_update_token` (string): A user password update linked to the session.

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_password_update_token`
-   `invalid_session_token`
-   `new_password_not_set`
-   `session_mismatch`
-   `user_identity_not_verified`

## Example

```
complete_user_password_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_password_update_token: "spjdfixngqtpu7y3ib22i34r.yc9gjp28k6v835vpf56uzfrf"
)
```
