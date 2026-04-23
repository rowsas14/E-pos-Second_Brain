<!--
meta:
  title: Sales POS / POS Checkout / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, pos-checkout, data-model]
-->
> Hub: [[10-modules/sales-pos/features/pos-checkout/overview]]

# POS Checkout - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **POS Checkout**.

## Primary entities
- sales
- sale_lines
- receipts

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/sales-pos/features/pos-checkout/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/pos-checkout/overview]] and [[business-rules]], then before [[application]] and [[api]].
