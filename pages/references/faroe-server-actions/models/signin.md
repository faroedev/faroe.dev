---
title: "signin model"
---

# signin model

## Fields

-   `id` (string)
-   `user_id` (string)
-   `user_first_factor_verified` (boolean): `true` if the user's first factor is verified.
-   `created_at` (timestamp): Timestamp of when the signin was created.
-   `expires_at` (timestamp): Timestamp of when the signin expires.

## Example

```
{
    id: "vgr9t89a3ndrsmr5wtb5c86j",
    user_id: "m2wymy7ssrzkbrwag9js8hcy",
    user_first_factor_verified: false,
    created_at: 2025-08-25T05:51:26Z,
    expires_at: 2025-08-25T06:21:26Z
}
```
