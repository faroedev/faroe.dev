---
title: "create_user_password_reset action"
---

# create_user_password_reset action

Create a user password reset with an email address. A temporary password is sent to the user's inbox.

The email addresses is not "normalized" (e.g. all lowercase) before processing.

## Parameters

-   `action_invocation_token` (string): Conditionally required
-   `user_email_address` (string)

## Return values

-   `user_password_reset` ([user_password_reset](/references/faroe-server-actions/models/user_password_reset))
-   `user_password_reset_token` (string)

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_email_address`
-   `rate_limited`
-   `user_disabled`
-   `user_not_found`

## Example

```
create_user_password_reset(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    user_email_address: "user@example.com"
)
```
