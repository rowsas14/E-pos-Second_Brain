<!--
meta:
  title: API Error Contract
  owner: Engineering / API
  status: active
  last_reviewed: 2026-04-22
  tags: [api, errors, contracts, validation, authorization]
-->

# API Error Contract

## Purpose

This file defines the client-visible API error model for the platform.

The goal is to make errors:

- useful for POS, admin, and e-commerce frontends
- consistent across modules
- safe for support and debugging
- not dependent on internal exception text or database messages

The backend direction already includes middleware and filter concepts for centralized handling.  
This error contract defines what the client should see.

## Error design principles

- one consistent error shape across modules
- clear difference between validation, authorization, not found, business, and conflict cases
- no leakage of stack traces, SQL details, or private internal implementation data
- enough structure for frontend flows and support investigation

## Recommended response shape

```json
{
  "success": false,
  "error": {
    "code": "business_rule_conflict",
    "message": "Return quantity exceeds the remaining eligible quantity.",
    "details": []
  }
}
```

`details` may be empty when a structured field-level breakdown is not relevant.

## Error categories

| Category | Meaning |
|---|---|
| validation error | request shape or field input is invalid |
| authentication error | caller is not authenticated |
| authorization error | caller authenticated but lacks required access |
| tenant-scope error | caller crossed tenant boundary or invalid tenant context |
| not-found error | target resource does not exist in allowed context |
| business rule conflict | request violates current business or workflow state |
| concurrency conflict | request conflicts with current state transition or write timing |
| server failure | unexpected failure that the client cannot resolve directly |

## Validation errors

Validation errors should be field-friendly.

Use when:

- required field missing
- invalid value format
- invalid request combination
- query parameter shape invalid

Preferred code example:

- `validation_failed`

## Authentication errors

Use when the caller is missing or has invalid credentials.

Preferred code example:

- `unauthenticated`

## Authorization errors

Use when the caller is authenticated but not allowed to perform the action.

Examples:

- missing permission
- wrong role scope
- feature not available for that operating context

Preferred codes may include:

- `forbidden`
- `feature_unavailable`

## Tenant-scope errors

Use when the request violates tenant or outlet boundary rules.

Examples:

- cross-tenant resource access
- outlet-scoped request outside active outlet boundary
- customer account used in the wrong tenant context

Preferred code examples:

- `tenant_scope_violation`
- `outlet_scope_violation`

## Not-found errors

Use when the resource does not exist **within the permitted context**.

Do not expose whether a resource exists in another tenant.

Preferred code example:

- `resource_not_found`

## Business rule conflicts

Use for operational or workflow violations.

Examples:

- till session already open
- payment allocation exceeds allowed amount
- return document source invalid
- exchange cannot complete in current status
- stocktake already posted
- requested action conflicts with document lifecycle

Preferred code examples:

- `business_rule_conflict`
- `invalid_state_transition`

## Concurrency conflicts

Use when a valid request loses a race against another change.

Examples:

- same till/session being closed twice
- conflicting stock-sensitive write
- repeated capture/refund attempt against already-updated financial state

Preferred code example:

- `concurrency_conflict`

See [concurrency-rules.md](./concurrency-rules.md).

## Server-side failures

Unexpected failures should not leak internal details.

Preferred client behavior:

- stable generic message
- correlation or trace identifier if implemented by backend support tooling
- detailed internal logging server-side only

Preferred code example:

- `server_error`

## HTTP status alignment

| Error type | Typical HTTP status |
|---|---|
| validation | 400 |
| unauthenticated | 401 |
| forbidden | 403 |
| not found | 404 |
| business or concurrency conflict | 409 |
| server failure | 500 |

Use the status that best matches the real condition. Do not hide all failures behind `200 OK`.

## Frontend usefulness rules

Error messages should support actual UI behavior for POS, admin, and storefront flows, while still allowing support teams to distinguish permission, tenant, workflow, and system failures.

## What must never be exposed

Do not expose stack traces, raw exception type names, SQL statements, internal infrastructure secrets, or cross-tenant existence hints.

## Related documents

- [request-response-standard.md](./request-response-standard.md)
- [auth-and-authorization.md](./auth-and-authorization.md)
- [concurrency-rules.md](./concurrency-rules.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
- [../07-backend/exception-handling-rules.md](../07-backend/exception-handling-rules.md)
