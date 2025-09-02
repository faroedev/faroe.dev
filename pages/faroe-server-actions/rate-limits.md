---
title: "Rate limits"
---

# Rate limits

While IP-based rate limits are not implemented, rate limits against user IDs and email addresses are implemented.

Here are all the rate limited actions:

-   Verify user password: 1 attempt per minute per user.
-   Send email: 1 attempt per 30 minutes per email address.
-   Verify email address verification code: 1 attempt per minute per email address.
-   Verify user password reset temporary password: 1 attempt per minute per user.
