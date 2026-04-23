<!--
meta:
  title: Payments / Provider Transactions / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, data-model]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Provider Transactions**.

## Primary entities
- payment_transactions

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/payments/features/provider-transactions/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[10-modules/payments/features/provider-transactions/overview]] and [[business-rules]], then before [[application]] and [[api]].
