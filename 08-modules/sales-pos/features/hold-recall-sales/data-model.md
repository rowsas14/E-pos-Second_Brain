<!--
meta:
  title: Sales POS / Hold & Recall Sales / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, hold-recall-sales, data-model]
-->
> Hub: [[10-modules/sales-pos/features/hold-recall-sales/overview]]

# Hold & Recall Sales - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Hold & Recall Sales**.

## Primary entities
- sales

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/sales-pos/features/hold-recall-sales/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/hold-recall-sales/overview]] and [[business-rules]], then before [[application]] and [[api]].
