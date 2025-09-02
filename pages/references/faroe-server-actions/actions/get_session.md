---
title: "get_session action"
---

# get_session action

Get a session.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)

## Return values

-   `session` ([session](/references/faroe-server-actions/models/session))

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`

## Examples

```
get_session(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7"
)
```
