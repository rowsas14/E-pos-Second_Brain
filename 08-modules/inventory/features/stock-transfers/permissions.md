<!--
meta:
  title: Inventory / Stock Transfers / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, permissions]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Permissions

## Purpose
This file explains role and permission behavior for **Stock Transfers**.

## Permission behavior
- inventory staff creates and processes transfers
- approval may require manager permission

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/inventory/features/stock-transfers/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-transfers/overview]] and before exposing [[api]] or [[frontend]] changes.
