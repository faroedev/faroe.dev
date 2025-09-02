---
title: "delete_signup action"
---

# delete_signup action

Delete a signup.

## Parameters

-   `action_invocation_id` (string)
-   `signup_token` (string)

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_signup_token`

## Example

```
delete_signup(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signup_token: "yjickd8enm8n5kitm86233yt.egewfuvjna78sxpmq4kv8zfn"
)
```
