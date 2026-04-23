<!--
meta:
  title: Payments / Payment Allocations / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payment-allocations, business-rules]
-->
> Hub: [[10-modules/payments/features/payment-allocations/overview]]

# Payment Allocations - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Payment Allocations** feature inside the **Payments** module.

## Core rules
- allocated totals must not exceed payment.captured_amount
- sale allocations require compatible inbound sale-purpose payment
- order allocations require compatible order-purpose payment

## Why these rules matter
A unified payment model still needs explicit linkage to business documents and over-allocation protection.

## Related feature files
- [[10-modules/payments/features/payment-allocations/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/payment-allocations/overview]], then before [[application]], [[api]], and [[validations]].
