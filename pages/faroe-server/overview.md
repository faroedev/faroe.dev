---
title: "Faroe server overview"
---

# Faroe server overview

Faroe is an auth server packaged as an open source Go package. Specifically, the package provides high-level APIs for creating an authentication server.

The server provides most of backend components in a modern auth system, including sessions, email address verification, passwords, rate limits, email address updates/resets, password updates and user deletion. It then exposes methods that can be called by client-side applications to sign in, validate session tokens, etc.

One important distinction from existing auth servers is that Faroe does not store your users. Users are handled by a dedicated user server. This server exposes a few basic methods to create, get, update, and delete users. Together with the Faroe auth server, they complete a full auth system for your application.

This architecture provides a big benefit. The user server is very simple and can be built by anyone. This gives you full control of your users, while letting Faroe handling everything else. You decide which attributes your users have and how they are stored.

The architecture also allows the package itself to be very flexible. There is no dependency on other tools, including databases. The storage layer is fully customizable and implementing it requires minimal code. The only external tools you need to bring are a some form of storage, an email server, and a way to expose the server to the internet.
