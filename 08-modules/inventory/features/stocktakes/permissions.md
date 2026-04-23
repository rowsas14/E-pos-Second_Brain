<!--
meta:
  title: Inventory / Stocktakes / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, permissions]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Permissions

## Purpose
This file explains role and permission behavior for **Stocktakes**.

## Permission behavior
- inventory staff counts
- posting may require manager or inventory lead permission

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/inventory/features/stocktakes/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/inventory/features/stocktakes/overview]] and before exposing [[api]] or [[frontend]] changes.
