---
title: "create_user_deletion action"
---

# create_user_deletion action

Create a user deletion linked to the session.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)

## Return values

-   `user_deletion` ([user_deletion](/references/faroe-server-actions/models/user_deletion))
-   `user_deletion_token` (string)

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`

## Example

```
create_user_deletion(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7"
)
```
