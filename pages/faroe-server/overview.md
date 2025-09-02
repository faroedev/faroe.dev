---
title: "Faroe server overview"
---

# Faroe server overview

Faroe is an auth server packaged as a Go package. Specifically, the package provides high-level APIs for creating an auth server.

The server provides most of backend components in a modern auth system, including sessions, email address verification, passwords, rate limiting, email address updates, password updates/resets, and user deletion. It exposes methods that can be called by client-side applications to sign in, validate session tokens, etc.

One important distinction from existing auth servers is that Faroe does not store your users. Users are handled by a dedicated user server. This server exposes a few basic methods to create, get, update, and delete users. Together with the Faroe auth server, they complete a full auth system for your application. This gives you full control of your users, while letting Faroe handling everything else. You decide which attributes your users have and how they are stored.

The architecture also allows the package itself to be very flexible. There is no dependency on other tools, including databases. The storage layer is fully customizable and implementing it requires minimal code. The only external tools you need to bring are a some form of storage, an email server, and a way to expose the server to the internet.

To get stated, see [Setup]() page to learn how to use the package. Or, if you want to try out the server first, see the [Quick-start guide]() to run an prebuilt server locally.