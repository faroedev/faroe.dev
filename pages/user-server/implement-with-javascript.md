---
title: "Implement user server with JavaScript"
---

# Implement user server with JavaScript

We provide an official package to make it easier to build user servers with JavaScript and TypeScript. This package works in the latest versions of Node.js, Deno, Bun, Cloudflare Workers, Netlify Edge Functions, and Vercel Edge Functions.

See the package [API reference](https://github.com/faroedev/js-user-server#api-reference) for details.

```
npm install @faroe/user-server
```

Implement the [`Actions`](https://github.com/faroedev/js-user-server#actions) interface.

```ts
interface Actions {
    createUserAction();
    getUserAction();
    getUserByEmailAddressAction();
    updateUserEmailAddressAction();
    updateUserPasswordHashAction();
    incrementUserSessionsCounterAction();
    deleteUserAction();
}
```

Example implementations using ORMs are available:

-   [Drizzle with MySQL](https://code.faroe.dev/js-user-server-actions-drizzle-mysql)
-   [Drizzle with PostgreSQL](https://code.faroe.dev/js-user-server-actions-drizzle-postgresql)
-   [Drizzle with SQLite](https://code.faroe.dev/js-user-server-actions-drizzle-sqlite)
-   [Prisma](https://code.faroe.dev/js-user-server-actions-prisma)

Example implementations using plain SQL are also available:

-   [MySQL](https://code.faroe.dev/js-user-server-actions-sql-mysql)
-   [PostgreSQL](https://code.faroe.dev/js-user-server-actions-sql-postgresql)
-   [SQLite](https://code.faroe.dev/js-user-server-actions-sql-sqlite)

Then, create a new [`Server`](https://github.com/faroedev/js-user-server#server) instance.

Use the `Server.resolveActionInvocationEndpointRequest()` to create an action invocation endpoint. It takes a request body of an action invocation request and returns the response body. It will return an `error` if the request is invalid.

**The action invocation endpoint should be protected and only accessible to trusted clients.** Some options are private networks and request signing.

```ts
// TODO: Protect route.

const server = new faroe_user_server.Server(actions);

let bodyJSON: string;

// Get request body

let responseBodyJSON: string;
try {
    responseBodyJSON = await server.resolveActionInvocationEndpointRequest(bodyJSON);
} catch {
    // Failed to parse JSON, unknown action, etc
    // Return 400 response
}

// Returns body
```

Example implementations are available:

-   [Astro](https://code.faroe.dev/js-user-server-action-invocation-endpoint-astro)
-   [Hono](https://code.faroe.dev/js-user-server-action-invocation-endpoint-hono)
-   [Next.js App Router](https://code.faroe.dev/js-user-server-action-invocation-endpoint-nextjs-app)
-   [Nuxt](https://code.faroe.dev/js-user-server-action-invocation-endpoint-nuxt)
-   [SvelteKit](https://code.faroe.dev/js-user-server-action-invocation-endpoint-sveltekit)
