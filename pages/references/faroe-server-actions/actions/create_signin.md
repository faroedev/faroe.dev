---
title: "create_signin action"
---

# create_signin action

Create a signin of the user identified with an email address.

The email addresses is not "normalized" (e.g. all lowercase) before processing.

## Parameters

-   `action_invocation_id` (string)
-   `user_email_address` (string): A valid email address.

## Return values

-   `signin` ([signin](/references/faroe-server-actions/models/signin))
-   `signin_token` (string)

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `invalid_email_address`
-   `user_disabled`
-   `user_not_found`

## Example

```
create_signin(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    email_address: "user@example.com"
)
```
