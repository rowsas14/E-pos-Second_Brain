<!--
meta:
  title: Receipts / Receipt Generation / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, data-model]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Receipt Generation**.

## Primary entities
- receipts

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/receipts/features/receipt-generation/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-generation/overview]] and [[business-rules]], then before [[application]] and [[api]].
