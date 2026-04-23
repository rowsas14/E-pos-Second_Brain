<!--
meta:
  title: Orders E-Commerce / Carts / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, edge-cases]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Carts**.

## Edge cases
- customer logs in after building guest cart
- cart expires while checkout is in progress

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/orders-ecommerce/features/carts/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
