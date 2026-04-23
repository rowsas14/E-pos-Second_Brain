<!--
meta:
  title: Exception Handling Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [exceptions, error-handling, middleware, api-safety]
-->

# Exception Handling Rules

## Purpose

This file defines backend exception handling rules for the project.

The uploaded backend direction shows API-level middleware and filters. This file explains how backend failures should be surfaced cleanly and safely through that global handling approach.

## Global handling direction

Use centralized handling for backend exceptions through:

- middleware
- global filters where appropriate
- shared error translation into API error responses

Do not scatter HTTP error formatting across controllers.

## Exception categories

| Category | Expected backend behavior |
|---|---|
| validation failure | return structured validation error response |
| authorization / forbidden | return safe auth failure response |
| not found | return clear not-found response without leaking internals |
| business rule conflict | return conflict or rule-specific safe error |
| tenant-scope violation | return safe scope/forbidden/conflict style error as appropriate |
| unexpected server failure | log internally, return safe server error response |

## What not to do

- do not expose stack traces to clients
- do not leak database internals in response messages
- do not let controllers build inconsistent error shapes manually
- do not use exceptions for normal branching where a controlled validation/result path is clearer

## Alignment with API contract

Backend exception handling must align with:

- [../05-api/error-contract.md](../05-api/error-contract.md)
- [../05-api/request-response-standard.md](../05-api/request-response-standard.md)

## Related documents

- [validation-rules.md](./validation-rules.md)
- [transaction-handling-rules.md](./transaction-handling-rules.md)
- [../05-api/error-contract.md](../05-api/error-contract.md)
- [../05-api/auth-and-authorization.md](../05-api/auth-and-authorization.md)
