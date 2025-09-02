---
title: "set_user_password_update_new_password action"
---

# set_user_password_update_new_password action

Set a user password update's new password.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_password_update_token` (string)
-   `password` (string): Between 10 and 100 characters.

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_password_length`
-   `invalid_password_update_token`
-   `invalid_session_token`
-   `new_password_already_set`
-   `session_mismatch`
-   `user_identity_not_verified`
-   `weak_password`

## Example

```
set_user_password_update_new_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_password_update_token: "spjdfixngqtpu7y3ib22i34r.yc9gjp28k6v835vpf56uzfrf",
    password: "SuperSecretPassword"
)
```
