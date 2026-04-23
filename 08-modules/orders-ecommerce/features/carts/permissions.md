<!--
meta:
  title: Orders E-Commerce / Carts / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, permissions]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - Permissions

## Purpose
This file explains role and permission behavior for **Carts**.

## Permission behavior
- customer self-service or anonymous guest flow

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/orders-ecommerce/features/carts/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/carts/overview]] and before exposing [[api]] or [[frontend]] changes.
