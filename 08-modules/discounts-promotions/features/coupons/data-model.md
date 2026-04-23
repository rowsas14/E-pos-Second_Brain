<!--
meta:
  title: Discounts & Promotions / Coupons / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, data-model]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Coupons**.

## Primary entities
- coupons
- coupon_redemptions

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/discounts-promotions/features/coupons/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/coupons/overview]] and [[business-rules]], then before [[application]] and [[api]].
