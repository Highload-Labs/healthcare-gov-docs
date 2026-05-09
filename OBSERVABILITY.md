# Observability

## Objective
Define the metrics, monitoring and tracing requirements needed to evaluate system behavior under load.

### Application Metrics
- Request rate (RPS)
- Request latency
- p50 / p95 / p99 latency
- Error rate

### Infrastructure Metrics
- CPU usage
- Memory usage
- Network throughput

### Load Generator Metrics
- Active VUs
- Iteration rate
- Load generator CPU usage
- Load generator memory usage

## Monitoring Stack
Initial monitoring tools:
- Grafana
- Pprof

## Logging Strategy
- Structured logging
- Request correlation IDs
- Avoid logging sensitive credentials or tokens

Notes: Future improvements may implemented.