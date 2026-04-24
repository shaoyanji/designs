# Error Handling Design

## Overview

This document outlines patterns for consistent error handling across the application.

## Error Categories

| Category | HTTP Status | Description |
|----------|-------------|-------------|
| Validation | 400 | Invalid input data |
| Authentication | 401 | Not authenticated |
| Authorization | 403 | Insufficient permissions |
| Not Found | 404 | Resource doesn't exist |
| Conflict | 409 | Resource already exists |
| Server | 500 | Internal server error |
| Service Unavailable | 503 | Temporary outage |

## Error Response Format

```json
{
  "error": {
    "code": "VALIDATION_FAILED",
    "message": "The request failed validation",
    "details": [
      {
        "field": "email",
        "issue": "Invalid email format"
      }
    ],
    "requestId": "req-abc123",
    "timestamp": "2024-01-15T10:30:00Z"
  }
}
```

## Error Codes

Standard error codes for client handling:
- `VALIDATION_FAILED` - Input validation error
- `UNAUTHENTICATED` - Missing/invalid credentials
- `PERMISSION_DENIED` - Insufficient permissions
- `RESOURCE_NOT_FOUND` - Requested resource missing
- `RATE_LIMITED` - Too many requests
- `INTERNAL_ERROR` - Unexpected server error
- `SERVICE_UNAVAILABLE` - Temporary service issue

## Client-Side Handling

### Strategies
1. **Retry with backoff** - For transient errors (503)
2. **User notification** - For validation errors
3. **Redirect to login** - For authentication errors
4. **Graceful degradation** - For non-critical failures

### Global Error Boundary
- Catch unexpected errors
- Display user-friendly message
- Log to error tracking service (Sentry)
- Option to retry or refresh

## Logging

Errors should log:
- Stack trace (server-side)
- Request context (user, endpoint)
- Error code and message
- Timestamp
- Correlation ID

Sensitive data must be redacted from logs.
