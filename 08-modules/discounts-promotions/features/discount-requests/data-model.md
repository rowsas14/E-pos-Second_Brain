<!--
meta:
  title: Discounts & Promotions / Discount Requests / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, data-model]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Discount Requests**.

## Primary entities
- discount_requests
- discount_types
- discount_scopes

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-requests/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-requests/overview]] and [[business-rules]], then before [[application]] and [[api]].
