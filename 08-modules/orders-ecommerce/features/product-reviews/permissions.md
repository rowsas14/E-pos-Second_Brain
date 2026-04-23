<!--
meta:
  title: Orders E-Commerce / Product Reviews / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, permissions]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Permissions

## Purpose
This file explains role and permission behavior for **Product Reviews**.

## Permission behavior
- customer submits own review
- tenant staff moderates reviews

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/orders-ecommerce/features/product-reviews/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/product-reviews/overview]] and before exposing [[api]] or [[frontend]] changes.
