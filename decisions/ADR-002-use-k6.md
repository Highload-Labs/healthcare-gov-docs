# ADR-002: Use K6 for Load Testing

## Status
Accepted

## Context
The project requires:
- High-concurrency load testing
- Distributed load generation
- Lightweight scripting and execution
- Observability integration
- Iterative scalability testing

## Decision
Use k6 as the primary load testing tool.

## Consequences
### Positive
- Lightweight and scriptable load testing
- Strong integration with Grafana
- Suitable for distributed load generation
- Efficient resource usage for large-scale testing

### Negative
- Distributed orchestration complexity at larger scale
- Load generators may become bottlenecks under extreme concurrency
- Realistic traffic modeling may require iterative refinement