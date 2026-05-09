# ADR-003: Reduced bcrypt Cost

## Status
Accepted

## Context
The project requires large-scale authentication load testing under constrained infrastructure resources (Trial AWS).

## Decision
Use reduced bcrypt cost factors during synthetic scalability testing iterations, while supporting configurable environments for production environments.

## Consequences
### Positive
- Maximum throughput for authentication and registration endpoints

### Negative
- Reduced resistance to offline brute-force attacks