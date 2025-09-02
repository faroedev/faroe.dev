---
title: "update_user_password_hash action"
---

# update_user_password_hash action

Update a user's password hash, password hash algorithm ID, and password salt, as well as increment a user's email address counter, if the user password hash counter matches.

## Parameters

-   `action_invocation_id` (string)
-   `user_id` (string)
-   `password_hash` (bytes)
-   `password_hash_algorithm_id` (string)
-   `password_salt` (bytes)
-   `user_password_hash_counter` (int32)

## Return values

None.

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `user_not_found`: The user doesn't exist or the user's password hash counter doesn't match.
