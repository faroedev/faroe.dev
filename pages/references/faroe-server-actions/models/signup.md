---
title: "signup model"
---

# signup model

## Fields

-   `id` (string)
-   `email_address` (string): A string that matches the pattern `[a-zA-Z0-9!#$%&'*+-/=?^_{|}~.]@[a-zA-Z0-9.-]` and is within 100 characters.
-   `email_address_verified` (boolean): `true` if the email address is verified.
-   `password_set` (boolean): `true` if the password is set.
-   `created_at` (timestamp): Timestamp of when the signup was created.
-   `expires_at` (timestamp): Timestamp of when the signup expires.

## Example

```
{
    id: "cf53jg7ee2pgwg668jnybjnb",
    email_address: "user@example.com",
    email_address_verified: false,
    password_set: false,
    created_at: 2025-08-25T05:51:26Z,
    expires_at: 2025-08-25T06:21:26Z
}
```
