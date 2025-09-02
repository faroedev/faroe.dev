---
title: "User deletions"
---

# User deletions

User deletions represent users' attempts to delete their account. They are tied to a single session.

The user deletion ID is a 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. This is a public ID. Do not treat this as a secret.

User deletion tokens should used be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

To complete the process and delete the user's account, the user must first verify their identity with their password.

User deletions are invalidated when the user is disabled, deleted, or changes their password.

They have an expiration of 10 minutes.