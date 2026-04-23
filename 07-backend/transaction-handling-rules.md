<!--
meta:
  title: Transaction Handling Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [transactions, unit-of-work, payments, inventory, workflow-safety]
-->

# Transaction Handling Rules

## Purpose

This file explains transaction boundaries for backend workflows that update multiple persistence concerns together.

This project contains several workflows where partial success is not acceptable.

## Why transaction discipline matters here

The platform includes business-sensitive operations such as:

- POS sale completion
- payment allocation
- refund creation
- exchange difference collection or refund
- stock movement creation
- return / exchange processing
- till session changes
- order and reservation state changes

A backend that commits those in the wrong order or outside a controlled boundary will create incorrect commerce records.

## Unit of Work rule

Use **Unit of Work** where a use case coordinates multiple repository actions that must succeed together.

Recommended direction:

- `IUnitOfWork` contract in Application common interfaces
- implementation in Infrastructure
- commit invoked by Application service at the correct use-case boundary

## Typical transaction-sensitive workflows

| Workflow | Why a transaction boundary matters |
|---|---|
| sale completion | sale header, lines, payment allocation, stock movement, receipt trigger may depend on one logical success path |
| refund workflow | refund row, outbound payment row, allocations, status updates must stay aligned |
| exchange completion | return, exchange, difference payment or refund, inventory updates must not drift apart |
| stock transfer posting | movement records and balance effects must remain consistent |
| till session close | closing values and session status must represent one committed state |

## Boundary rule

The transaction boundary should be at the **use-case level**, not inside one low-level repository method when the business workflow spans more than one repository.

## Rollback expectation

If one step in a transaction-sensitive workflow fails, the backend should not leave:

- orphaned payment allocations
- partial stock movements
- mismatched return and refund state
- half-completed exchange records
- invalid session states

## Related documents

- [application-layer-rules.md](./application-layer-rules.md)
- [repository-rules.md](./repository-rules.md)
- [infrastructure-layer-rules.md](./infrastructure-layer-rules.md)
- [exception-handling-rules.md](./exception-handling-rules.md)
- [../04-data/schema-principles.md](../04-data/schema-principles.md)
- [../05-api/concurrency-rules.md](../05-api/concurrency-rules.md)
- [../05-api/idempotency-rules.md](../05-api/idempotency-rules.md)
