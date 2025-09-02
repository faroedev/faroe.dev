---
title: "complete_signin action"
---

# complete_signin action

Issues a new session using a signin. The signin must be set as user first factor verified. The used signin is invalidated.

## Parameters

-   `action_invocation_id` (string)
-   `signin_token` (string)

## Return values

-   `session` ([session](/references/faroe-server-actions/models/session))
-   `session_token` (string)

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_signin_token`
-   `user_first_factor_not_verified`

## Example

```
complete_signin(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signin_token: "jbrjgdnt7ti7uu3z4q56si76.ipvdkynjgjx2626px6w4gyzc"
)
```
