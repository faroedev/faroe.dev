---
title: "User email address updates"
---

# User email address updates

User email address updates represent users' attempts to update their email address. They are tied to a single session.

User email address updates are identified with unique identifier. It will always be a 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. Do not treat this as a secret.

User email address update tokens should used be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

The new email address cannot be changed after its creation.

To complete the process and update the user's email address, the user must first verify their new email address with the email address verification code. Then they must verify their identity with their password.

The email address verification code is a 8 character string consisting of uppercase letters (A-Z) and digits (0-9). It is randomly generated using a cryptographically-secure pseudo-random source and has 40 bits of entropy.

User email address updates are invalidated when the user is disabled, deleted, changes their email address, or changes their password.

They have an expiration of 20 minutes.