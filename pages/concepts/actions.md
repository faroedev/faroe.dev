---
title: "Actions"
---

# Actions

Actions are procedures or functions in the server designed to be called by other servers. They take a list of arguments and either return some values or an error (defined by their error code). They provide an RPC-like API.

Servers can make actions invocable by exposing an [action invocation endpoint]().  

## Types

Actions take and return values in these types:

-   int32, int64
-   string
-   bytes
-   boolean
-   null
-   object
-   list
