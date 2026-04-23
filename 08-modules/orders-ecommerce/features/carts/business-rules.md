<!--
meta:
  title: Orders E-Commerce / Carts / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, business-rules]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Carts** feature inside the **Orders E-Commerce** module.

## Core rules
- cart may belong to customer or guest_token
- status can be active, converted, abandoned, or expired
- cart totals are recalculated from items and pricing rules

## Why these rules matter
E-Commerce requires an intermediate cart state that is separate from completed orders and supports guest checkout.

## Related feature files
- [[10-modules/orders-ecommerce/features/carts/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/carts/overview]], then before [[application]], [[api]], and [[validations]].
