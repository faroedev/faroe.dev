---
title: "Users"
---

# Users

## Overview

Users are at the core of Faroe. Everything is based around and works on top of it.

They're identified by a unique case-sensitive string ID and their case-sensitive email address.

## Counters

Users have a few counter attributes:

-   Email address counter
-   Password hash counter
-   Sessions counter
-   Disabled counter

The email address, password hash, and disabled counter are incremented when the user's email address, password hash, disabled flag respectively are updated. This is critical in maintaining the security of the system.

Incrementing the sessions counter will invalidate all current sessions tied to the user.

## Disabled users

Users can be disabled by setting the disabled flag. All disabled users will be immediately locked out from their account and will not be able to sign in or reset their password..
