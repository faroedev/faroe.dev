---
title: "Sessions"
---

# Sessions

## Get current session

Use the [`get_session`]() action to get the current session.

```
session = get_session(
    session_token
)
```

## Sign out

Use the [`delete_session`]() action to delete the current session.

```
delete_session(
    session_token
)
```

## Sign out all devices

Use the [`delete_all_sessions`]() action to delete all sessions of the user.

```
delete_all_session(
    session_token
)
```
