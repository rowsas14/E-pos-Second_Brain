<!--
meta:
  title: Inventory / Stock Transfers / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, data-model]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Stock Transfers**.

## Primary entities
- stock_transfers
- stock_transfer_lines
- stock_movements

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/inventory/features/stock-transfers/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-transfers/overview]] and [[business-rules]], then before [[application]] and [[api]].
