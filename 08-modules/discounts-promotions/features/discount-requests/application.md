<!--
meta:
  title: Discounts & Promotions / Discount Requests / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, application]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Discount Requests**.

## Main orchestration paths
- raise discount request
- manager reviews request
- approved request flows into discount application

## Application-layer notes
- keep request lifecycle separate from actual discount write model

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
