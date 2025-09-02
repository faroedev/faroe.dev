---
title: "update_user_email_address action"
---

# update_user_email_address action

Update a user's email address and increment a user's email address counter if the email address counter matches.

## Parameters

-   `action_invocation_id` (string)
-   `user_id` (string)
-   `email_address` (string)
-   `user_email_address_counter` (int32)

## Return values

None.

## Error codes

-   `email_address_already_used`: A user with the exact email address (with same letter casing) already exists.
-   `internal_conflict`
-   `internal_error`
-   `user_not_found`: The user doesn't exist or the user's email address counter doesn't match.
