<!--
meta:
  title: Inventory / Stock Ledger / Workflows
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-ledger, workflows]
-->
> Hub: [[10-modules/inventory/features/stock-ledger/overview]]

# Stock Ledger - Workflows

## Purpose
This file captures the operational **workflow** for **Stock Ledger** across user, system, and integration steps.

## Main workflows
- post sale-out movement
- post return-in or adjustment movement
- rebuild or reconcile projection balance if needed

## Workflow dependencies
- [[business-rules]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/inventory/features/stock-transfers/overview|Stock Transfers]]
- [[10-modules/inventory/features/stocktakes/overview|Stocktakes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-ledger/overview]] and [[business-rules]]; combine with [[application]] for end-to-end implementation.
