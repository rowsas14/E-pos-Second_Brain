<!--
meta:
  title: Receipts / Receipt Delivery / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, data-model]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Receipt Delivery**.

## Primary entities
- receipts

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/receipts/features/receipt-delivery/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-delivery/overview]] and [[business-rules]], then before [[application]] and [[api]].
