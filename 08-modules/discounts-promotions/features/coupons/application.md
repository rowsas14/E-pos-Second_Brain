<!--
meta:
  title: Discounts & Promotions / Coupons / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, application]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Coupons**.

## Main orchestration paths
- create coupon
- activate coupon
- redeem coupon against order or sale where allowed

## Application-layer notes
- coupon validation and redemption must be atomic enough to protect use limits

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
