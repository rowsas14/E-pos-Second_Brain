<!--
meta:
  title: Inventory / Stock Ledger / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-ledger, business-rules]
-->
> Hub: [[10-modules/inventory/features/stock-ledger/overview]]

# Stock Ledger - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Stock Ledger** feature inside the **Inventory** module.

## Core rules
- stock movement quantity is stored as positive value; movement type determines direction
- inventory_balances is projection state, not historical truth
- all stock records are outlet and variant scoped

## Why these rules matter
Stock mismatch across channels is a major project risk. Ledger-first modeling is the chosen control mechanism.

## Related feature files
- [[10-modules/inventory/features/stock-ledger/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/inventory/features/stock-transfers/overview|Stock Transfers]]
- [[10-modules/inventory/features/stocktakes/overview|Stocktakes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-ledger/overview]], then before [[application]], [[api]], and [[validations]].
