<!--
meta:
  title: Inventory / Stocktakes / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, data-model]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Stocktakes**.

## Primary entities
- stocktakes
- stocktake_lines
- stock_movements

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/inventory/features/stocktakes/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/inventory/features/stocktakes/overview]] and [[business-rules]], then before [[application]] and [[api]].
