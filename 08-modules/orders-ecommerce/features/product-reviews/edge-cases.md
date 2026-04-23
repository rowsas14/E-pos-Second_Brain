<!--
meta:
  title: Orders E-Commerce / Product Reviews / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, edge-cases]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Product Reviews**.

## Edge cases
- customer reviews archived product
- duplicate review policy for same purchase not yet defined

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/orders-ecommerce/features/product-reviews/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
