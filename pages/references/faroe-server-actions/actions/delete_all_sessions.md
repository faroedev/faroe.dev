---
title: "delete_all_sessions action"
---

# delete_all_sessions action

Delete all sessions linked to a session's user.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`

## Example

```
delete_all_sessions(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7"
)
```
