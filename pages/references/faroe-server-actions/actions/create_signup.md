---
title: "create_signup action"
---

# create_signup action

Create a new signup and sends the signup email address verification code to the email address. The email address must not be tied to an existing user.

The email addresses is not "normalized" (e.g. all lowercase) before processing.

Users are not prevented from using "tricks" that allow them to use the same "base" email address to create multiple accounts (e.g. using `+` or `.` in Google account email addresses).

## Parameters

-   `action_invocation_id` (string)
-   `email_address` (string): A string that matches the pattern `[a-zA-Z0-9!#$%&'*+-/=?^_{|}~.]@[a-zA-Z0-9.-]` and is within 100 characters.

## Return values

-   `signup` ([signup](/references/faroe-server-actions/models/signup))
-   `signup_token` (string)

## Error codes

-   `email_address_already_used`
-   `email_address_not_allowed`: The email address is blocked.
-   `internal_conflict`
-   `internal_error`
-   `invalid_email_address`
-   `rate_limited`

## Example

```
create_signup(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    email_address: "user@example.com"
)
```
