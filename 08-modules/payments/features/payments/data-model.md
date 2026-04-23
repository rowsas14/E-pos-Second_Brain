<!--
meta:
  title: Payments / Payments / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, data-model]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Payments**.

## Primary entities
- payments
- payment_method_types
- payment_statuses

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/payments/features/payments/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[10-modules/payments/features/payments/overview]] and [[business-rules]], then before [[application]] and [[api]].
