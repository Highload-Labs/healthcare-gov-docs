# POST /auth/register

## Request
Headers: `Content-Type: application/json`

| Field      | Type   | Required | Constrains                                          |
|------------|--------|----------|-----------------------------------------------------|
| `email`    | string | Yes      | Unique, Valid email format, max 255 chars           |
| `password` | string | Yes      | 8-72 chars, must include number, hashed with Bcrypt |
| `username` | string | Yes      | Alphanumeric, 3-20 chars                            |

## Response
- 201 Created
```json
{
  "success": true,
  "data": {
    "user_id": "uuid-v4-string",
    "created_at": "2026-05-12T15:00:00Z"
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

- 409 Conflict (User Exists)
```json
{
  "success": false,
  "code": "CONFLICT",
  "message": "This email address is already registered."
}
```