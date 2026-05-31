# POST /enrollments

## Request
Headers: 
- `Content-Type: application/json`
- `Authorization: Bearer <access_token>`

| Field     | Type   | Required | Constraints |
|-----------| ------ | -------- |-------------|
| `plan_id` | string | Yes      | UUID        |

```json
{
  "plan_id": "uuid"
}
```

## Response

- 201 Created
```json
{
  "success": true,
  "data": {
    "id": "uuid",
    "plan_id": "uuid",
    "effective_date": "2027-01-01T00:00:00Z",
    "end_date": "2027-12-31T23:59:59Z"
  }
}
```

- 400 Bad Request
```json
{
  "success": false,
  "code": "BAD_REQUEST",
  "message": "Invalid enrollment request."
}
```

- 401 Unauthorized
```json
{
  "success": false,
  "code": "UNAUTHORIZED",
  "message": "Invalid or expired access token."
}
```

- 404 Not Found
```json
{
  "success": false,
  "code": "NOT_FOUND",
  "message": "Plan not found."
}
```

- 409 Conflict
```json
{
  "success": false,
  "code": "CONFLICT",
  "message": "User already has an active enrollment."
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

## Note:
- Success won't return plan details. To get a plan details, please refer to [this endpoint](https://github.com/Highload-Labs/healthcare-gov-docs/blob/main/api/plans.md#get-plansid).