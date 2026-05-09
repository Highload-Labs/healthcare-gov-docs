# Threat Model

## Objective
- Learning and Implementing STRIDE with SSDLC Iterative Agile.

## Scope
This threat model applies to:
- Authentication services
- Registration services
- Session and token handling
- User data retrieval APIs
- Load testing infrastructure

## Assets
- User credentials
- Session tokens
- Authentication state
- User session data
- Infrastructure resources
- Availability of authentication services

## Trust Boundaries
- External clients -> API services

## STRIDE Analysis
### Spoofing
| Threat                               | Impact            | Initial Mitigation           |
|--------------------------------------|-------------------|------------------------------|
| Session token impersonation          | Session hijacking | Signed tokens and expiration |

### Tampering
| Threat                | Impact                  | Initial Mitigation |
|-----------------------|-------------------------|--------------------|
| Modified API payloads | Invalid system behavior | Input validation   |
| Token manipulation    | Authentication bypass   | Token validation   |

### Repudiation
| Threat                  | Impact                | Initial Mitigation      |
|-------------------------|-----------------------|-------------------------|
| Missing request tracing | Reduced observability | Request correlation IDs |

### Information Disclosure
| Threat                             | Impact                       | Initial Mitigation                   |
|------------------------------------|------------------------------|--------------------------------------|
| Sensitive token exposure           | Account compromise           | Token expiration                     |
| Excessive API error details        | Internal information leakage | Sanitized error response             |
| Misconfigured authorization access | User data exposure           | User-scoped authorization validation |

### Denial of Service
| Threat                                         | Impact              | Initial Mitigation     |
|------------------------------------------------|---------------------|------------------------|
| Excessive authentication requests by single IP | CPU exhaustion      | Rate limiting          |
| Spike traffic overwhelming API services        | Service unavailable | Horizontal autoscaling |

### Elevation of Privilege
| Threat                            | Impact              | Initial Mitigation               |
|-----------------------------------|---------------------|----------------------------------|
| Improper authorization validation | Unauthorized access | Server-side authorization checks |