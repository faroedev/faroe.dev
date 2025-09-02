---
title: "verify_user_deletion_user_password action"
---

# verify_user_deletion_user_password action

Verify a user deletion user password and set it as user identity verified.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_deletion_token` (string)
-   `user_password` (string)

## Return values

None.

## Error codes

-   `incorrect_password`
-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_deletion_token`
-   `rate_limited`
-   `session_mismatch`
-   `user_identity_already_verified`

## Example

```
verify_user_deletion_user_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_deletion_token: "7g5sykd36dq82gag96xn3jya.23sp3k9b72u4t5e6yfpiw8qi",
    user_password: "SuperSecretPassword"
)
```
