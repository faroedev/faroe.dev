---
title: "create_user_email_address_update action"
---

# create_user_email_address_update action

Create a new user email address update linked to the session.

The new email address is not "normalized" (e.g. all lowercase) before processing.

## Parameters

-   `action_invocation_id` (string)
-   `session_token` (string)
-   `new_email_address` (string)

## Return values

-   `user_email_address_update` ([user_email_address_update](/references/faroe-server-actions/models/user_email_address_update))
-   `user_email_address_update_token` (string)

## Error codes

-   `email_address_already_used`
-   `email_address_not_allowed`
-   `internal_conflict`
-   `internal_error`
-   `invalid_email_address`
-   `invalid_session_token`
-   `rate_limited`

# Example

```
create_user_email_address_update(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    session_token: "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7",
    new_email_address: "user@example.com"
)
```
