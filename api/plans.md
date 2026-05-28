# Plans API

## GET /plans?zipcode=

### Request

Headers: None

| Query Parameter | Type   | Required | Constraints          |
| --------------- | ------ | -------- | -------------------- |
| `zipcode`       | string | Yes      | 5 numeric characters |

### Response

- 200 OK

```json
{
    "success": true,
    "data": [
        {
            "id": "plan_001",
            "name": "Silver Care Basic",
            "provider": "Healthcare Gov",
            "tier": "Silver",
            "monthly_premium": 249.99,
            "deductible": 1500,
            "out_of_pocket_max": 7500
        },
        {
            "id": "plan_002",
            "name": "Gold Care Plus",
            "provider": "Healthcare Gov",
            "tier": "Gold",
            "monthly_premium": 399.99,
            "deductible": 750,
            "out_of_pocket_max": 5000
        }
    ]
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
    "message": "No plans available for this zipcode."
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

This endpoint returns all available healthcare plans for the specified zipcode.

Returned plans may vary depending on regional coverage availability.

---

## GET /plans/:id

### Request

Headers: None

| Parameter | Type   | Required | Constraints   |
| --------- | ------ | -------- | ------------- |
| `id`      | string | Yes      | Valid plan ID |

### Response

- 200 OK

```json
{
    "success": true,
    "data": {
        "id": "plan_001",
        "name": "Silver Care Basic",
        "provider": "Healthcare Gov",
        "tier": "Silver",
        "monthly_premium": 249.99,
        "deductible": 1500,
        "out_of_pocket_max": 7500,
        "benefits": [
            "Emergency Services",
            "Prescription Drugs",
            "Preventive Care"
        ]
    }
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

- 500 Internal Server Error

```json
{
    "success": false,
    "code": "INTERNAL_ERROR",
    "message": "Internal Server Error."
}
```

### Behavior

This endpoint returns detailed information about a healthcare plan based on its identifier.
