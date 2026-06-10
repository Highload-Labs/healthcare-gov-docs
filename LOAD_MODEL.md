# Load Model

## Objective
The Platform must support up to 250,000 concurrent active users during peak enrollment periods.

## Load Type
- Spike Testing
- Distributed load generation using k6

## Assumed User Journey
The full workflow for this platform are:
1. Register
2. Login
3. Check Coverage
4. Browse Plans
5. View Plan Details
6. Enroll

## User Behavior Assumptions
Average session during: 5 minutes (300 seconds)
This duration is included the full workflow from registration through enrollment.

## Derived Traffic Model
Concurrent Active Users: 250,000 users
Average Session Duration: 300 seconds
Estimated completed workflow per seconds: 250,000 / 300 = ~834 workflow/sec
Average requests per workflow: 6 requests
Estimated sustained request rate: 833 * 6 = ~5.000 RPS

## Performance Target
Please refer into this [SLO document](https://github.com/Highload-Labs/healthcare-gov-docs/blob/main/SLO.md) for reliability and performance targets.

## Load Generation Strategy
- Distributed k6 workers
- Horizontal scaling of load generators

## Metrics Collected
Metrics are collected with Prometheus and Grafana.
- Request rate (RPS)
- p95 / p99 latency
- Error rate
- CPU / Memory usage
