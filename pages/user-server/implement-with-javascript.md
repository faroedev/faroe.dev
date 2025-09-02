---
title: "Implement user server with JavaScript"
---

# Implement user server with JavaScript

We provide an official package to make it easier to build user servers with JavaScript and TypeScript. This package works in the latest versions of Node.js, Deno, Bun, Cloudflare Workers, Netlify Edge Functions, and Vercel Edge Functions.

```
npm install @faroe/user-server
```

Implement the [`Actions`]() interface.

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

-   [Drizzle with MySQL]()
-   [Drizzle with PostgreSQL]()
-   [Drizzle with SQLite]()
-   [Prisma]()

Example implementations using plain SQL are also available:

-   [MySQL]()
-   [PostgreSQL]()
-   [SQLite]()

With `faroe_user_server.Actions`, create a new [`ActionInvocationRequestResolver`]() instance and create an [action invocation endpoint]().

`ActionInvocationRequestResolver.resolveRequest()` takes a request body of an action request endpoint and returns the response body. It will throw an `Error` if the request body was invalid.

```ts
const resolver = new faroe_user_server.ActionInvocationRequestResolver(actions);

let bodyJSON: string;

// Get request body

let responseBodyJSON: string;
try {
    responseBodyJSON = await resolver.resolveRequest(bodyText);
} catch {
    // Failed to parse JSON, unknown action, etc
    // Return 400 response
}

// Returns body
```

Example implementations are available:

-   [Astro]()
-   [Hono]()
-   [Next.js App Router]()
-   [Nuxt]()
-   [SvelteKit]()
