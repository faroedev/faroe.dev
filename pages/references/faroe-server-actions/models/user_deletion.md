---
title: "user_deletion model"
---

# user_deletion model

## Fields

-   `id` (string)
-   `user_id` (string)
-   `session_id` (string)
-   `user_identity_verified` (boolean): `true` if the user's identity is verified.
-   `created_at` (timestamp): A timestamp of when the signup was created.
-   `expires_at` (timestamp): A timestamp of when the signup expires.

## Example

```
{
    id: "2mwe2e3ihz6ktm5puegeryhe",
    user_id: "m2wymy7ssrzkbrwag9js8hcy",
    session_id: "w93zmrzat9xc82wwr9vt5sy4",
    user_identity_verified: false,
    created_at: 2025-08-25T05:51:26Z,
    expires_at: 2025-08-25T06:21:26Z
}
```
