---
title: "User password resets"
---

# User password resets

User password resets represent users' attempts to reset their password.

The user password resets ID is a 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. This is a public ID. Do not treat this as a secret.

User password resets tokens should used be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

To complete the process and reset the user's password, the user must first verify their identity with the temporary password of the user password reset sent to the user's inbox. Then they must set their new password.

User password updates are invalidated when the user is disabled, deleted, changes their email address, or changes their password.

The temporary password is a 12-character string consisting of uppercase letters (A-Z) and digits (0-9). It is randomly generated using a cryptographically-secure pseudo-random source and has 60 bits of entropy.

They have an expiration of 20 minutes.
