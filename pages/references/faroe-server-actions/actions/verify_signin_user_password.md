---
title: "verify_signin_user_password action"
---

# verify_signin_user_password action

Verifies a signin's user password and sets it as user first factor verified.

## Parameters

-   `action_invocation_id` (string)
-   `signin_token` (string)
-   `password` (string)

## Error codes

-   `incorrect_password`
-   `internal_conflict`
-   `internal_error`
-   `invalid_signin_token`
-   `rate_limited`
-   `user_first_factor_already_verified`

## Example

```
verify_signin_user_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signin_token: "jbrjgdnt7ti7uu3z4q56si76.ipvdkynjgjx2626px6w4gyzc",
    password: "SuperSecretPassword"
)
```
