<!--
meta:
  title: Receipts / Receipt Delivery / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, permissions]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Permissions

## Purpose
This file explains role and permission behavior for **Receipt Delivery**.

## Permission behavior
- cashier triggers print
- customer or admin triggers download/email depending on policy

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/receipts/features/receipt-delivery/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-delivery/overview]] and before exposing [[api]] or [[frontend]] changes.
