---
title: "complete_user_password_reset action"
---

# complete_user_password_reset action

Resets a user's password. The user password reset must be set as user first factor verified.

Existing signins, user email address updates, user password updates, user deletion, and user password resets are invalidated. **Existing sessions are not invalidated.**

## Parameters

-   `action_invocation_id` (string)
-   `user_password_reset_token` (string)

## Return values

-   `session` ([session](/references/faroe-server-actions/models/session))
-   `session_token` (string)

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_user_password_reset_token`
-   `new_password_not_set`
-   `session_not_created`: The user's password was successfully updated but a session couldn't be created.
-   `user_first_factor_not_verified`

## Example

```
complete_user_password_reset(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    user_password_reset_token: "5py2ybbxs4rabkkahzsda6tb.at8ti6uwqfn53dd5p7p7kncn"
)
```
