---
title: "session model"
---

# session model

## Fields

-   `id` (string)
-   `user_id` (string)
-   `created_at` (timestamp): Timestamp of when the session was created.
-   `expires_at` (timestamp, null): Timestamp of when the session expires. This is only defined if sessions are configured to have an absolute timeout. Sessions may expire before this timestamp due to inactivity.

## Example

```
{
    "id": "w93zmrzat9xc82wwr9vt5sy4",
    "user_id": "m2wymy7ssrzkbrwag9js8hcy",
    created_at: 2025-08-25T05:51:26Z,
    expires_at: null
}
```
