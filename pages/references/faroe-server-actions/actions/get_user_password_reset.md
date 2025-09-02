---
title: "get_user_password_reset action"
---

# get_user_password_reset action

Get a user password reset.

## Parameters

-   `action_invocation_id` (string)
-   `user_password_reset_token` (string)

## Return values

-   `user_password_reset` ([user_password_reset](/references/faroe-server-actions/models/user_password_reset))

## Error codes

- `internal_error`
- `invalid_user_password_reset_token`

## Example

```
get_user_password_reset(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    user_password_reset: "5py2ybbxs4rabkkahzsda6tb.at8ti6uwqfn53dd5p7p7kncn"
)
```
