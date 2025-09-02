---
title: "get_signin action"
---

# get_signin action

Get a signin.

## Parameters

-   `action_invocation_id` (string)
-   `signin_token` (string)

## Return values

-   `signin` ([signin](/references/faroe-server-actions/models/signin))

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_signin_token`

## Example

```
create_signin(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signin_token: "jbrjgdnt7ti7uu3z4q56si76.ipvdkynjgjx2626px6w4gyzc"
)
```
