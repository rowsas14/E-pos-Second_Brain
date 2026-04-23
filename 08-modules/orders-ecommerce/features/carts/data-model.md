<!--
meta:
  title: Orders E-Commerce / Carts / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, data-model]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Carts**.

## Primary entities
- carts
- cart_items

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/orders-ecommerce/features/carts/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/carts/overview]] and [[business-rules]], then before [[application]] and [[api]].
