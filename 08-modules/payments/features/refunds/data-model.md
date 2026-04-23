<!--
meta:
  title: Payments / Refunds / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, data-model]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Refunds**.

## Primary entities
- refunds

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/payments/features/refunds/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/refunds/overview]] and [[business-rules]], then before [[application]] and [[api]].
