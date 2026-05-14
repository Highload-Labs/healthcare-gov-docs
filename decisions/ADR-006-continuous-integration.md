# ADR-006: Adopt Continuous Integration Workflow with GitHub Actions

## Status
Accepted

## Context
This project uses STRIDE threat modeling, and we identified that current codebase was affected by a log injection vulnerability related to Repudiation ([#10](https://github.com/Highload-Labs/healthcare-gov-backend/issues/10)).

The project was also affected by Auth Bypass and DoS that identified in the Go standard library/runtime.

Manual verification alone is insufficient for maintaining consistent quality and security checks across pull requests.

## Decision
Adopt GitHub Actions as the Continuous Integration (CI) platform.

The CI Workflows runs:
- gofmt
- go vet
- gosec
- govulncheck
- go test

Then, the workflow will be executed on:
- push
- pull_request

targeting the `main` branch.

## Consequences
### Positive
- Consistent code quality checks
- Early detection of security issues
- Early detection of vulnerable dependencies/runtime
- Reduced manual verification effort

### Negative
- Vendor lock-in
- Longer feedback cycle compared to local-only development