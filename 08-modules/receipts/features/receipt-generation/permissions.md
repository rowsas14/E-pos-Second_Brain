<!--
meta:
  title: Receipts / Receipt Generation / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, permissions]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - Permissions

## Purpose
This file explains role and permission behavior for **Receipt Generation**.

## Permission behavior
- system generates; authorized staff/customer accesses according to document visibility

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/receipts/features/receipt-generation/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-generation/overview]] and before exposing [[api]] or [[frontend]] changes.
