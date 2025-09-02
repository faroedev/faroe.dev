---
title: "complete_user_deletion action"
---

# complete_user_deletion action

Delete a user. The user deletion must bse set as user identity verified.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `user_deletion_token` (string): A user deletion linked to the session.

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_session_token`
-   `invalid_user_deletion_token`
-   `invalid_session_mismatch`
-   `user_identity_not_verified`

## Example

```
complete_user_deletion(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    user_deletion_token: "7g5sykd36dq82gag96xn3jya.23sp3k9b72u4t5e6yfpiw8qi"
)
```
