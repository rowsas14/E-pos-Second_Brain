<!--
meta:
  title: Inventory / Stock Ledger / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-ledger, application]
-->
> Hub: [[10-modules/inventory/features/stock-ledger/overview]]

# Stock Ledger - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Stock Ledger**.

## Main orchestration paths
- post sale-out movement
- post return-in or adjustment movement
- rebuild or reconcile projection balance if needed

## Application-layer notes
- movement posting belongs in domain/application orchestration of sales, returns, transfers, and stocktake
- use transaction boundaries and idempotent posting patterns

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/inventory/features/stock-transfers/overview|Stock Transfers]]
- [[10-modules/inventory/features/stocktakes/overview|Stocktakes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
