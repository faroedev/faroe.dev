---
title: "Action invocation endpoint"
---

# Action invocation endpoint

An action invocation endpoint is a POST endpoint that invokes an action and returns its result.

How implementations should protect their endpoints is not strictly defined. However, we recommend putting rate limits for public endpoints and adding authentication to private endpoints exposed publicly.

## Request body

-   `action` (string): The name of the action to invoke.
-   `arguments` (object): An object with key-value pairs representing the parameter names and their corresponding values. See the serialization section for details on serializing action values to JSON values.

### Example

```json
{
    "action": "get_session",
    "arguments": {
        "session_token": "w93zmrzat9xc82wwr9vt5sy4.g9nepmvhg6sdsqebqcepyib7"
    }
}
```

## Successful response

A 200 response indicates that the action was successfully invoked and produced a result.

If the action succeeds, the response body is a JSON object with the following fields:

-   `ok` (boolean): Set to `true`.
-   `action_invocation_id` (string)
-   `values` (object): The return values from the action. See the serialization section for details on how action values are serialized to JSON values.

If the action errors, the response body is a JSON object with the following fields:

-   `ok` (boolean): Set to `false`.
-   `action_invocation_id` (string)
-   `error_code` (string): The error code from the action.

### Example

```json
{
    "ok": true,
    "action_invocation_id": "mka2rsawyu3vds3j9cxwgr54",
    "values": {
        "session": {
            "id": "w93zmrzat9xc82wwr9vt5sy4",
            "user_id": "m2wymy7ssrzkbrwag9js8hcy",
            "created_at": 1756101086,
            "expires_at": null
        }
    }
}
```

```json
{
    "ok": false,
    "action_invocation_id": "mka2rsawyu3vds3j9cxwgr54",
    "error_code": "invalid_session_token"
}
```

## Error response

Only 2xx response statuses are reserved. The endpoint may return any 4xx or 5xx response to indicate that it could not or did not invoke the requested action. Some examples include:

-   A 400 response to indicate an invalid action name.
-   A 400 response to indicate a missing argument or invalid argument type.
-   A 401 response to indicate invalid request credentials.
-   A 503 response to indicate the server is down.

## Serialization

Action types are mapped to the following JSON types:

-   int32, int64: number
-   string: string
-   bytes: Base64 encoded string (padding required)
-   boolean: boolean
-   timestamp: unix timestamp in seconds
-   object: object
-   list: array
-   null: null
