---
title: "User server"
---

# User server

A user server is a dedicated server for your users. It exposes an [action invocation endpoint](/references/action-invocation-endpoint) for [user server actions](/references/user-server-actions). These actions include:

-   `create_user`
-   `get_user`
-   `get_user_by_email_address`
-   `update_user_email_address`
-   `update_user_password_hash`
-   `increment_user_sessions_counter`
-   `delete_user`

Guides for implementing the server is available:

-   [Go](/user-server/implement-with-go)
-   [JavaScript/TypeScript](/user-server/implement-with-javascript)
