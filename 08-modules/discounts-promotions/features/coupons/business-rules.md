<!--
meta:
  title: Discounts & Promotions / Coupons / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, business-rules]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Coupons** feature inside the **Discounts & Promotions** module.

## Core rules
- coupon code unique within tenant
- status moves through draft, active, inactive, expired
- max uses and per-customer caps are optional

## Why these rules matter
E-Commerce and promotional campaigns require reusable code-based discounting under tenant control.

## Related feature files
- [[10-modules/discounts-promotions/features/coupons/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/coupons/overview]], then before [[application]], [[api]], and [[validations]].
