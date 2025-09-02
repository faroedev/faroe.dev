---
title: "delete_user_password_reset action"
---

# delete_user_password_reset action

Delete a user password reset.

## Parameters

-   `action_invocation_id` (string)
-   `user_password_reset_token` (string)

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_user_password_reset_token`

## Example

```
delete_user_password_reset(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    user_password_reset: "5py2ybbxs4rabkkahzsda6tb.at8ti6uwqfn53dd5p7p7kncn"
)
```
