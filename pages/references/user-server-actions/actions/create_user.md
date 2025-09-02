---
title: "create_user action"
---

# create_user action

Create a new user. The email address should be stored as-is, with the casing preserved.

## Parameters

-   `action_invocation_id` (string)
-   `email_address` (string)
-   `password_hash` (bytes)
-   `password_hash_algorithm_id` (string)
-   `password_salt` (bytes)

## Return values

-   `user` ([user](/references/user-server-actions/models/user))

## Error codes

-   `email_address_already_used`: A user with the exact email address (with same letter casing) already exists.
-   `internal_conflict`
-   `internal_error`
