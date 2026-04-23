<!--
meta:
  title: Inventory / Stock Ledger / Frontend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-ledger, frontend]
-->
> Hub: [[10-modules/inventory/features/stock-ledger/overview]]

# Stock Ledger - Frontend

## Purpose
This file captures **frontend** behavior, screens, and UI integration points for **Stock Ledger**.

## Frontend behavior notes
- admin stock ledger and balance views; not cashier-facing
- surface available, on-hand, and reserved separately

## Frontend dependency map
- [[10-modules/inventory/features/stock-ledger/overview]] for scope
- [[workflows]] for user flow
- [[permissions]] for access behavior
- [[api]] for contract usage
- [[edge-cases]] for failure state design

## Related features
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/inventory/features/stock-transfers/overview|Stock Transfers]]
- [[10-modules/inventory/features/stocktakes/overview|Stocktakes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-ledger/overview]], [[workflows]], [[permissions]], and [[api]].
