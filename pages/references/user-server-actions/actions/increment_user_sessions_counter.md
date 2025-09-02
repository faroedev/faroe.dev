---
title: "increment_user_sessions_counter action"
---

# increment_user_sessions_counter action

Increment a user's sessions counter if the user's sessions counter matches.

## Parameters

-   `action_invocation_id` (string)
-   `user_id` (string)
-   `user_sessions_counter` (int32)

## Return values

None.

## Error codes

-   `email_address_already_used`
-   `internal_conflict`
-   `internal_error`
-   `user_not_found`: The user doesn't exist or the user's sessions counter doesn't match.
