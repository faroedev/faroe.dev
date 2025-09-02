---
title: "Faroe server Javascript client library"
---

# Faroe server Javascript client library

Install the package from NPM:

```
npm i @faroe/client
```

Initialize a new `Client` instance with the action invocation endpoint client.

See the package [API reference]() for details.

```ts
import * as faroe_client from "@faroe/client";

const actionInvocationEndpointClient = new ActionInvocationEndpointClient()

const client = new faroe_client.Client(actionInvocationEndpointClient);

const result = await client.createSignup(emailAddress);
if (!result.ok) {
    console.log(result.actionInvocationId, result.signup, result.signupToken);
} else {
    console.log(result.actionInvocationId, result.errorCode);
}
```

```ts
class ActionInvocationEndpointClient implements faroe_client.ActionInvocationEndpointClient {
    public async sendActionInvocationEndpointRequest(body) {
        // Handle authentication, etc
        const response = await fetch(endpoint, {
            method: "POST",
            body: body,
        });
        if (response.status !== 200) {
            if (response.body !== null) {
                await response.body.cancel();
            }
            throw new Error(`Unknown status ${response.status}`);
        }
        const resultJSON = await response.text();
        return resultJSON;
    }
}
```