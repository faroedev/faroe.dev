---
title: "Quick-start guide"
---

# Quick-start guide

Creating a Faroe server using the package may be a bigger commitment than some people are ready to make. If you want to try out the Faroe server locally before using the package, we recommend running the [Faroe local server](https://github.com/faroedev/local-server).

This is a bare-bones Faroe implementation with everything stored in memory. It is only for local testing and **should not be used in production.**

You can either clone the project if you have Go installed already, or install a pre-built binary from [GitHub releases](https://github.com/faroedev/local-server/releases/latest).

```
https://github.com/pilcrowonpaper/malta/releases/latest/download/darwin-amd64.tgz
https://github.com/pilcrowonpaper/malta/releases/latest/download/darwin-arm64.tgz
https://github.com/pilcrowonpaper/malta/releases/latest/download/linux-amd64.tgz
https://github.com/pilcrowonpaper/malta/releases/latest/download/linux-arm64.tgz
https://github.com/pilcrowonpaper/malta/releases/latest/download/windows-386.tgz
https://github.com/pilcrowonpaper/malta/releases/latest/download/windows-amd64.tgz
```

Start the server by passing the port number and your user server action invocation endpoint.

See the [user server overview](/user-server/overview) page for details on user servers. No authentication is required for the action invocation endpoint.

```
go run . 3001 "https://localhost:3000/user/invoke-action"

./local-server 3001 "https://localhost:3000/user/invoke-action"
```

`/` is the action invocation endpoint (`http://localhost:3001` on port 3001).

## What's missing for production?

-   **The user server action invocation endpoint is unprotected.**
-   Only one CPU core is used for hashing passwords.
-   No IP-based rate limits or Captchas in front of the Faroe server action invocation endpoint.
-   Go maps are used for storage. You may ran out of memory since the size of these maps are uncapped.
