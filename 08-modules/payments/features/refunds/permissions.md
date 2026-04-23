<!--
meta:
  title: Payments / Refunds / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, permissions]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Permissions

## Purpose
This file explains role and permission behavior for **Refunds**.

## Permission behavior
- refund creation requires authorized role

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/payments/features/refunds/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/refunds/overview]] and before exposing [[api]] or [[frontend]] changes.
