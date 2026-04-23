<!--
meta:
  title: Payments / Payment Allocations / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payment-allocations, validations]
-->
> Hub: [[10-modules/payments/features/payment-allocations/overview]]

# Payment Allocations - Validations

## Purpose
This file records input, business, and **workflow** validations for **Payment Allocations**.

## Validation rules
- validate payment compatibility and remaining allocable amount
- prevent duplicate sale-payment or order-payment pair records

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
