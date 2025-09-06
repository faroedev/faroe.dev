---
title: "Faroe server overview"
---

# Faroe server overview

Faroe is an auth server packaged as a Go package. Specifically, the package provides high-level APIs for creating an auth server.

Like any other auth server, client-side applications can use it to sign in, sign up, validate session tokens, etc. It covers many aspects of your application, including:

-   Sign up with email address verification
-   Password sign in
-   Sessions
-   User email address update with email address verification
-   User password update
-   User password reset
-   User deletion

One important distinction from existing servers is that Faroe does not directly store your users. Instead, you define a light abstraction over your app's database that allows Faroe to perform basic CRUD (create, read, update, delete) operations on your users. This gives you full control over your user data. You define the attributes your users have, how they're stored, and how they're managed.

Alternatively, you may create a separate user server (possibly in a different language) to handle queries to your app's database. In this setup, Faroe will make HTTP requests to your user server to interact with your user data.

This also means that only ephemeral data is stored on the server. Even in a worst-case scenario such as complete data loss, your users would simply need to sign in again. There's no big overhead in maintaining the server.

This architecture also removes the need of a complex storage layer in the server and the package is designed to work with any key-value storage. The package is lightweight and can be deployed anywhere with any type of storage - all you need is just an email server.

To get stated, see [Setup](/faroe-server/setup) page to learn how to use the package. Or, if you want to try out the server first, see the [Quick-start guide](/faroe-server/quickstart-guide) to run an prebuilt server locally.

Join our [Discord server](https://discord.gg/hEW2kwc8Jv) if you have any questions!
