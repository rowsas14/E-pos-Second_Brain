<!--
meta:
  title: Orders E-Commerce / Product Reviews / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, data-model]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Product Reviews**.

## Primary entities
- reviews

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/orders-ecommerce/features/product-reviews/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/product-reviews/overview]] and [[business-rules]], then before [[application]] and [[api]].
