<!--
meta:
  title: Idempotency Rules
  owner: Engineering / API / Payments
  status: active
  last_reviewed: 2026-04-22
  tags: [api, idempotency, payments, retries, write-safety]
-->

# Idempotency Rules

## Purpose

This file defines duplicate-safe API behavior for retry-prone write operations.

This project’s schema already supports payment-level idempotency through an `idempotency_key`.  
That makes idempotency a real platform concern, not a theoretical API preference.

## Why this matters in this platform

Duplicate writes are especially dangerous in this system because they can affect:

- payment capture
- refund payout creation
- exchange-difference collection
- checkout-related financial writes
- other operations where network retries or client resubmission can occur

A duplicate-safe API prevents the same logical request from creating multiple financial effects.

## Primary idempotency area

The most important current area is the unified payment model.

Related docs:

- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../04-data/schema-principles.md](../04-data/schema-principles.md)

## Operations that need idempotency attention

| Operation type | Why it matters |
|---|---|
| payment creation/capture | duplicate submission can create double collection attempts |
| refund initiation | duplicate request can create double payout attempts |
| exchange-difference collection | retry can over-collect or duplicate payment records |
| checkout completion tied to payment | client retries can produce duplicate financial side effects |

## API rule

Where a workflow is retry-prone and has money movement impact, the API should support idempotent handling.

Example route style:

- `POST /api/v1/payments`
- `POST /api/v1/refunds`
- `POST /api/v1/exchanges/{exchangeId}/collect-difference`

## Example request concept

```http
POST /api/v1/payments
Idempotency-Key: 6f56a8bb-7e2f-4c13-9d6b-123456789abc
```

The exact transport location may be header-based or otherwise standardized by implementation, but it must be used consistently where the backend supports idempotent replay behavior.

## Expected behavior

If the same logical request is retried with the same idempotency key:

- the API should not create a second independent financial effect
- the API should return the original or equivalent safe result
- the API should surface conflicts clearly if the key is reused for a materially different request body

## What idempotency is not

Idempotency does not replace:

- business validation
- permission checks
- tenant checks
- concurrency handling

It solves duplicate submission safety, not all transaction correctness concerns.

See [concurrency-rules.md](./concurrency-rules.md).

## Body mismatch rule

If the same idempotency key is reused with a meaningfully different request, that should be treated as a conflict rather than silently accepted.

## Scope rule

Idempotency handling must still remain tenant-aware.  
A key used in one valid request context must not allow unsafe cross-tenant behavior.

## Related documents

- [api-overview.md](./api-overview.md)
- [concurrency-rules.md](./concurrency-rules.md)
- [error-contract.md](./error-contract.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../02-architecture/backend-architecture.md](../02-architecture/backend-architecture.md)
