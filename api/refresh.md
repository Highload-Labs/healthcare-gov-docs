# POST /auth/refresh

## Request
Headers: `Authorization: Bearer <refresh_token>`

Payload:
None

## Response
- 200 OK
Note: Upon calling this, the old refresh token becomes useless immediately. And, this EP issues both of refresh token and access token.

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

- 401 Unauthorized
```json
{
    "success": false,
    "code": "UNAUTHORIZED",
    "message": "Invalid or expired refresh token."
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

### Behavior
Please refer to this [login.md](https://github.com/Highload-Labs/healthcare-gov-docs/blob/main/api/login.md) for token behavior.