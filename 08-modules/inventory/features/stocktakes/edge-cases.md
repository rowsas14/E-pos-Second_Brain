<!--
meta:
  title: Inventory / Stocktakes / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, edge-cases]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Stocktakes**.

## Edge cases
- stock movement happens while count is in progress
- cancel count after partial line entry

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/inventory/features/stocktakes/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
