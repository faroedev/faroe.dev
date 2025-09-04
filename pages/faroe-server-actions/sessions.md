---
title: "Sessions"
---

# Sessions

Also see [Sessions](/concepts/sessions) concept page.

## Get current session

Use the [`get_session`](/references/faroe-server-actions/actions/get_session) action to get the current session.

```
session = get_session(
    session_token
)
```

## Sign out

Use the [`delete_session`](/references/faroe-server-actions/actions/delete_session) action to delete the current session.

```
delete_session(
    session_token
)
```

## Sign out all devices

Use the [`delete_all_sessions`](/references/faroe-server-actions/actions/delete_all_sessions) action to delete all sessions of the user.

```
delete_all_session(
    session_token
)
```
