# ADR-001: Use Go for Backend Services

## Status
Accepted

## Context
The project requires:
- High concurrency handling
- Efficient memory usage
- Lightweight deployment
- Strong observability support
- Suitable for CPU-Bound

## Decision
Use Go as the primary backend language.

## Consequences
### Positive
- Efficient goroutine-based concurrency
- Good runtime observability
- Strong standard library support
- Low deployment complexity
- Small Docker image size

### Negative
- Manual optimization may still be required under high load
- Additional Complexity when performing low-level performance optimizations