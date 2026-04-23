<!--
meta:
  title: Payments / Payment Allocations / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payment-allocations, permissions]
-->
> Hub: [[10-modules/payments/features/payment-allocations/overview]]

# Payment Allocations - Permissions

## Purpose
This file explains role and permission behavior for **Payment Allocations**.

## Permission behavior
- normally system-driven through checkout flows; manual correction requires finance/ops authorization

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/payments/features/payment-allocations/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/payment-allocations/overview]] and before exposing [[api]] or [[frontend]] changes.
