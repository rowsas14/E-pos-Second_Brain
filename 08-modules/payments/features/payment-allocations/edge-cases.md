<!--
meta:
  title: Payments / Payment Allocations / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payment-allocations, edge-cases]
-->
> Hub: [[10-modules/payments/features/payment-allocations/overview]]

# Payment Allocations - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Payment Allocations**.

## Edge cases
- split payment across methods
- partial capture then later additional capture

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/payments/features/payment-allocations/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
