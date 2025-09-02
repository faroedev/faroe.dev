---
title: "User password updates"
---

# User password updates

User password updates represent users' attempts to update their password. They are tied to a single session.

The user password update ID is a a 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. Do not treat this as a secret.

User password update tokens should used be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

To complete the process and update the user's password, the user must first verify their identity with their password. Then they must set their new password. The new password can only be set once.

User password updates are invalidated when the user is disabled, deleted, or changes their password.

They have an expiration of 10 minutes.
