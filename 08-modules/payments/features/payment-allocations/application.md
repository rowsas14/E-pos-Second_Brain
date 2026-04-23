<!--
meta:
  title: Payments / Payment Allocations / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payment-allocations, application]
-->
> Hub: [[10-modules/payments/features/payment-allocations/overview]]

# Payment Allocations - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Payment Allocations**.

## Main orchestration paths
- allocate payment on POS completion
- allocate payment on order placement or later capture

## Application-layer notes
- allocation service belongs close to transaction completion flows, with strict invariants

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
