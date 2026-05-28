# GET /coverage/:zipcode

## Request
Headers: None

| Parameter | Type   | Required | Constraints          |
| --------- | ------ | -------- | -------------------- |
| `zipcode` | string | Yes      | 5 numeric characters |

## Response
- 200 OK
```json
{
    "success": true,
    "data": {
        "zipcode": "32024",
        "state": "Florida",
        "supported": true
    }
}
```

- 400 Bad Request

```json
{
    "success": false,
    "code": "BAD_REQUEST",
    "message": "Invalid zipcode format."
}
```

- 404 Not Found

```json
{
    "success": false,
    "code": "NOT_FOUND",
    "message": "Coverage is not available for this zipcode."
}
```

- 500 Internal Server Error

```json
{
    "success": false,
    "code": "INTERNAL_ERROR",
    "message": "Internal Server Error."
}
```

## Behavior
This endpoint is used to verify whether a zipcode is supported by the platform before browsing or enrolling into healthcare plans.

If the zipcode is supported, the API returns regional coverage information associated with the zipcode.
