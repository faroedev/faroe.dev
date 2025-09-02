---
title: "get_user_by_email_address action"
---

# get_user_by_email_address action

Get a user by email address. The email address must match exactly, including letter casing.

## Parameters

-   `action_invocation_id` (string)
-   `email_address` (string)

## Return values

-   `user` ([user](/references/user-server-actions/models/user))

## Error codes

-   `internal_conflict`
-   `internal_error`
-   `user_not_found`
