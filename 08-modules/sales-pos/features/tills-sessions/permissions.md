<!--
meta:
  title: Sales POS / Tills & Sessions / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, permissions]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Permissions

## Purpose
This file explains role and permission behavior for **Tills & Sessions**.

## Permission behavior
- cashier opens/closes own session subject to role rules
- manager can review and override close discrepancies

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/sales-pos/features/tills-sessions/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/tills-sessions/overview]] and before exposing [[api]] or [[frontend]] changes.
