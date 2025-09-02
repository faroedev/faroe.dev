---
title: "verify_user_password_reset_temporary_password action"
---

# verify_user_password_reset_temporary_password action

Verify a user password reset's temporary password and set it as user identity verified.

## Parameters

-   `action_invocation_id` (string)
-   `user_password_reset_token` (string)
-   `temporary_password` (string)

## Return values

None.

## Error codes

-   `incorrect_temporary_password`
-   `internal_conflict`
-   `internal_error`
-   `invalid_user_password_reset_token`
-   `rate_limited`
-   `user_first_factor_already_verified`

## Example

```
verify_user_password_reset_temporary_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    user_password_reset: "5py2ybbxs4rabkkahzsda6tb.at8ti6uwqfn53dd5p7p7kncn",
    temporary_password: "G2RKQXXE4Q5T"
)
```
