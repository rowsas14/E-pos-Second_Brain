<!--
meta:
  title: Discounts & Promotions / Coupons / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, edge-cases]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Coupons**.

## Edge cases
- coupon reaches max uses during checkout race condition
- same customer tries multiple carts with same coupon

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/discounts-promotions/features/coupons/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
