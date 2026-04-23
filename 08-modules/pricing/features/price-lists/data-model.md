<!--
meta:
  title: Pricing / Price Lists / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, data-model]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Price Lists**.

## Primary entities
- price_lists
- price_list_items

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/pricing/features/price-lists/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/pricing/features/price-lists/overview]] and [[business-rules]], then before [[application]] and [[api]].
