---
title: "Signins"
---

# Signins

Signins represent users' sign-in attempts.

The signin ID is 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. Do not treat this as a secret.

Signin tokens should be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

Signins are invalidated when the user is disabled or updates their password.

To complete the sign-in process and exchange the signin for a session, the signin user's first factor must be verified using their password.

They have an expiration of 10 minutes.