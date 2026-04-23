<!--
meta:
  title: Payments / Provider Transactions / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, permissions]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - Permissions

## Purpose
This file explains role and permission behavior for **Provider Transactions**.

## Permission behavior
- system writes provider events; support/finance may read

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/payments/features/provider-transactions/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[10-modules/payments/features/provider-transactions/overview]] and before exposing [[api]] or [[frontend]] changes.
