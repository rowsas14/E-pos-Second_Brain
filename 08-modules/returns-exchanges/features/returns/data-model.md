<!--
meta:
  title: Returns & Exchanges / Returns / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, data-model]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Returns**.

## Primary entities
- returns
- return_lines
- return_refund_allocations
- return_reason_codes

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/returns-exchanges/features/returns/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/returns-exchanges/features/returns/overview]] and [[business-rules]], then before [[application]] and [[api]].
