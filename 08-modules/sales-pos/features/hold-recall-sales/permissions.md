<!--
meta:
  title: Sales POS / Hold & Recall Sales / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, hold-recall-sales, permissions]
-->
> Hub: [[10-modules/sales-pos/features/hold-recall-sales/overview]]

# Hold & Recall Sales - Permissions

## Purpose
This file explains role and permission behavior for **Hold & Recall Sales**.

## Permission behavior
- cashier can hold and recall within allowed scope
- manager may void abandoned held sales

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/sales-pos/features/hold-recall-sales/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/hold-recall-sales/overview]] and before exposing [[api]] or [[frontend]] changes.
