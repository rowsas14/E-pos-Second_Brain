<!--
meta:
  title: Concurrency Rules
  owner: Engineering / API / Backend
  status: active
  last_reviewed: 2026-04-22
  tags: [api, concurrency, conflicts, transactions, state]
-->

# Concurrency Rules

## Purpose

This file defines how the platform should handle API-level conflicts when two valid operations collide in time or state.

This is especially important in a commerce platform where several users or clients may act on:

- the same till/session
- the same payment or refund flow
- the same inventory-sensitive operation
- the same return or exchange document
- the same status transition

## Why this matters

Without clear concurrency rules, valid requests can still create inconsistent business results.

This system contains multiple sensitive areas where timing matters more than simple CRUD behavior.

## High-risk conflict areas

| Area | Example conflict |
|---|---|
| till/session | two requests attempt to close the same open session |
| payments | repeated or overlapping allocation or refund attempts |
| inventory-sensitive workflows | overlapping stock-affecting actions on the same document flow |
| returns/exchanges | same return processed twice or conflicting exchange completion |
| document status transitions | multiple attempts to move the same document into different states |

## API expectations

The API should:

- detect invalid current-state transitions
- avoid silently accepting conflicting writes
- return structured conflict responses
- keep conflict handling safe for operators and clients

See [error-contract.md](./error-contract.md).

## Till/session conflicts

Till and session work is highly sensitive because POS is operational and cashier-facing.

Examples:

- closing an already-closed session
- opening a second active session where only one active session is allowed
- posting cash movement against an invalid session state

Related docs:

- [../08-modules/sales-pos/](../08-modules/sales-pos/)
- [../04-data/database-overview.md](../04-data/database-overview.md)

## Payment and allocation conflicts

Payments, payment allocations, and refunds must not exceed valid captured or allocatable amounts.

Conflicts can occur when:

- two requests allocate against the same payment
- refund totals exceed allowed captured amounts
- a state change makes the original request no longer valid

## Inventory-sensitive conflicts

The data model includes a ledger + projection approach for inventory.  
That makes inventory changes especially sensitive to document state and transaction order.

Conflicts can occur during:

- stock transfer processing
- stocktake posting
- return restock handling
- reservation and release flows
- sale or exchange inventory effects

## State transition conflicts

Document-based workflows should reject impossible or repeated transitions.

Examples:

- approving an already-cancelled request
- posting an already-posted stocktake
- completing an already-completed exchange

## Client-visible behavior

When a conflict occurs, the API should return a clear conflict response rather than generic failure text.

Preferred code example:

- `concurrency_conflict`
- `invalid_state_transition`

Use HTTP `409` where the condition is truly a conflict.

## Relationship to idempotency

Concurrency and idempotency are related but not identical.

| Concern | Focus |
|---|---|
| idempotency | safe handling of repeated identical requests |
| concurrency | safe handling of overlapping or conflicting valid requests |

See [idempotency-rules.md](./idempotency-rules.md).

## Implementation expectation

Conflict prevention and detection may require a mix of:

- validation of current document state
- transaction-safe backend handling
- allocation and quantity guard rules
- database and service-layer coordination

This file defines API-visible expectations, not low-level locking mechanics.

## Related documents

- [idempotency-rules.md](./idempotency-rules.md)
- [error-contract.md](./error-contract.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
- [../08-modules/README.md](../08-modules/README.md)
