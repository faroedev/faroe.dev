---
title: "complete_signup action"
---

# complete_signup action

Create a new user from a signup's email address and password. It also issues a new session.

## Parameters

-   `action_invocation_token` (string):
-   `signup_token` (string)

## Return values

-   `session` ([session](/references/faroe-server-actions/models/session))
-   `session_token` (string)

## Error codes

-   `email_address_not_verified`
-   `internal_conflict`
-   `internal_error`
-   `invalid_signup_token`
-   `session_not_created`: The user was successfully created but a session couldn't be created. 
-   `password_not_set`

## Example

```
complete_signup(
    action_invocation_id: "mka2rsawyu3vds3j9cxwgr54",
    signup_token: "yjickd8enm8n5kitm86233yt.egewfuvjna78sxpmq4kv8zfn"
)
```
