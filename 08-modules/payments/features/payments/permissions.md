<!--
meta:
  title: Payments / Payments / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, permissions]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Permissions

## Purpose
This file explains role and permission behavior for **Payments**.

## Permission behavior
- cashier or checkout flow creates allowed inbound payments
- refund payments require authorized roles

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/payments/features/payments/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[10-modules/payments/features/payments/overview]] and before exposing [[api]] or [[frontend]] changes.
