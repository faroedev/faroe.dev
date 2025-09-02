---
title: "user_password_reset model"
---

# user_password_reset model

## Fields

-   `id` (string)
-   `user_id` (string)
-   `user_first_factor_verified` (boolean): `true` if the temporary password was verified.
-   `new_password_set` (boolean): `true` if the new user password is set.
-   `created_at` (timestamp): A timestamp of when the signup was created.
-   `expires_at` (timestamp): A timestamp of when the signup expires.

## Example

```
{
    id: "2mwe2e3ihz6ktm5puegeryhe",
    user_id: "m2wymy7ssrzkbrwag9js8hcy",
    session_id: "w93zmrzat9xc82wwr9vt5sy4",
    user_first_factor_verified: false,
    new_password_set: false,
    created_at: 2025-08-25T05:51:26Z,
    expires_at: 2025-08-25T06:21:26Z
}
```
