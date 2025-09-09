---
title: "Sessions"
---

# Sessions

## Overview

The session ID is a 24-character case-sensitive string composed of lowercase letters (a–z) and digits (0–9). This is a public ID. Do not treat this as a secret.

Session tokens should be for authentication. The token is a 49-character case-sensitive string composed of lowercase letters (a-z), digits (0-9), and periods (.). Tokens should be safely stored in the client.

Sessions are invalidated when the user is disabled or deleted.

## Expiration

Sessions have an inactivity timeout and optionally an absolute expiration.

Inactivity timeout controls how long an inactive session remains valid. It is based on when the session's token was last used. Keep in mind that the server does not update its last-used record every time a token is used to reduce writes to storage. Instead, it's only periodically updated based on the activity check interval configuration.

Note that the expiration is not hard-coded to individual sessions. Expiration timestamps are calculated using the current server configuration, and not based on the configuration when the session was created.

## Session validation caching

The server gets the current state of the user when validating sessions. You can enable caching to temporarily cache the user state (1-5 minutes) to reduce how often user checks are performed. See [`SessionConfigStruct.UserCacheExpiration`](https://pkg.go.dev/github.com/faroedev/faroe#SessionConfigStruct.UserCacheExpiration).
