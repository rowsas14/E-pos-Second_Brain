<!--
meta:
  title: Discounts & Promotions / Discount Applications / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-applications, application]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-applications/overview]]

# Discount Applications - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Discount Applications**.

## Main orchestration paths
- apply approved discount
- apply direct policy discount
- recompute affected totals

## Application-layer notes
- pricing snapshot and total recalculation must happen inside source sale/order orchestration

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]
- [[10-modules/discounts-promotions/features/coupons/overview|Coupons]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
