---
title: "delete_signin action"
---

# delete_signin action

Delete a signin.

## Parameters

-   `action_invocation_id` (string)
-   `signin_token` (string)

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_signin_token`

## Example

```
delete_signin(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signin_token: "jbrjgdnt7ti7uu3z4q56si76.ipvdkynjgjx2626px6w4gyzc"
)
```
