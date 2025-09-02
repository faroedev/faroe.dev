---
title: "create_user action"
---

# create_user action

Create a new user. THe email address should be stored in a case-sensitive format.

## Parameters

-   `action_invocation_id` (string)
-   `email_address` (string)
-   `password_hash` (bytes)
-   `password_hash_algorithm_id` (string)
-   `password_salt` (bytes)

## Return values

-   `user` ([user](/references/user-server-actions/models/user))

## Error codes

-   `email_address_already_used`
-   `internal_conflict`
-   `internal_error`
