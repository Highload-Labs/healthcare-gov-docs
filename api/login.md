# POST /auth/login



## Request

Headers: `Content-Type: application/json`



| Field      | Type   | Required | Constrains                        |
|------------|--------|----------|-----------------------------------|
| `email`    | string | Yes      | Valid email format, max 255 chars |
| `password` | string | Yes      | 8-72 chars, must include number   |



## Response

- 200 OK
```json
{
    "success": true,
    "data": {
        "access_token": "string",
        "refresh_token": "string",
        "expires_in": 3600
    }
}
```

- 400 Bad Request
```json
{
    "success": false,
    "code": "BAD_REQUEST",
    "message": "Missing required fields."
}
```

- 401 Unauthorized
```json
{
    "success": false,
    "code": "UNAUTHORIZED",
    "message": "Incorrect email or password."
}

```

## Token Expiration
### Session Lifetimes
- access_token is valid for 3600 second (1 hour)
- refresh_token is valid for 7 days

### Behavior
When the `access_token` expired, the client muse use `refresh_token` at the `/auth/refresh/` endpoint to receive a new `access_token`. But, if `refresh_token` also expired then the user must re-login via `/auth/login`

