<!--
meta:
  title: Inventory / Stock Ledger / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-ledger, backend]
-->
> Hub: [[10-modules/inventory/features/stock-ledger/overview]]

# Stock Ledger - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- movement posting belongs in domain/application orchestration of sales, returns, transfers, and stocktake
- use transaction boundaries and idempotent posting patterns

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/inventory/features/stock-ledger/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/inventory/features/stock-transfers/overview|Stock Transfers]]
- [[10-modules/inventory/features/stocktakes/overview|Stocktakes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
