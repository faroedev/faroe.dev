---
title: "Signups"
---

# Signups

Signups represent users' sign-up attempts.

The signup ID is a 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. Do not treat this as a secret.

Signup tokens should be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

To complete the sign-up process and exchange the signin for a session, the user must first verify their email address with the email address verification code. Then they must set their password.

The email address verification code is a 8 character string consisting of uppercase letters (A-Z) and digits (0-9). It is randomly generated using a cryptographically-secure pseudo-random source and has 40 bits of entropy.

They have an expiration of 20 minutes.