# GET /healthz

## Request
None

## Response
- 200 OK
```json
{
  "status": true
}
```

## Notes
- The endpoint should remain lightweight and avoid expensive operations.
- Initial implementation does not verify external dependencies such as databases or caches.

## Degraded Conditions
- If the application process is unable to handle requests, the endpoint may return non-200 responses or become unreachable.