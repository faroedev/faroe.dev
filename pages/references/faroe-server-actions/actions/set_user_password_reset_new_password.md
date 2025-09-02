---
title: "set_user_password_reset_new_password action"
---

# set_user_password_reset_new_password action

Set a user password reset's new password.

## Parameters

-   `action_invocation_id` (string)
-   `user_password_reset_token` (string)
-   `password` (string): Between 10 and 100 characters.

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_password_length`
-   `invalid_user_password_reset_token`
-   `new_password_already_set`
-   `user_first_factor_not_verified`
-   `weak_password`

## Example

```
set_user_password_reset_new_password(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    user_password_reset: "5py2ybbxs4rabkkahzsda6tb.at8ti6uwqfn53dd5p7p7kncn",
    password: "SuperSecretPassword"
)
```
