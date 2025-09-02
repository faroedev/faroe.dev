---
title: "User server actions"
---

# User server actions

## Input validation

Because user server actions are intended to be used by trusted clients (i.e. a Faroe server you own/trust), no input validation is required. The size of each values should be negotiated between the user server and the faroe server. 

If a user server encounters a value that it cannot handle (e.g. too large for the database column), it should handled as an unexpected internal error.

## Actions

-   [create_user](/references/user-server-actions/actions/create_user)
-   [delete_user](/references/user-server-actions/actions/delete_user)
-   [get_user_by_email_address](/references/user-server-actions/actions/get_user_by_email_address)
-   [get_user](/references/user-server-actions/actions/get_user)
-   [increment_user_sessions_counter](/references/user-server-actions/actions/increment_user_sessions_counter)
-   [update_user_email_address](/references/user-server-actions/actions/update_user_email_address)
-   [update_user_password_hash](/references/user-server-actions/actions/update_user_password_hash)

## Models

-   [user](/references/user-server-actions/models/user)
