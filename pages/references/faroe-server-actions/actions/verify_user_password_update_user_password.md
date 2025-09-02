---
title: "verify_user_password_update_user_password action"
---

# verify_user_password_update_user_password action

Verify a user password update's user password and set it as user identity verified.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_password_update_token` (string)
-   `password` (string)

## Return values

None.

## Error codes

-   `incorrect_password`
-   `internal_conflict`
-   `internal_error`
-   `invalid_password_update_token`
-   `invalid_session_token`
-   `rate_limited`
-   `session_mismatch`
-   `user_identity_already_verified`

## Example

```
verify_user_password_update_user_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_password_update_token: "spjdfixngqtpu7y3ib22i34r.yc9gjp28k6v835vpf56uzfrf",
    password: "SuperSecretPassword"
)
```
