# ADR-004: Use Stateless API Design

## Status
Accepted

## Context
The project requires:
- Services must scale horizontally as load increase.
- Any node should be able to handle incoming requests.

## Decision
Use stateless API service design where possible, with externalized session-related state management.

## Consequences
### Positive
- Any server can handle any request
- Easier horizontal scaling

### Negative
- Increase on payload size
- Relying on external database or caches for shared state