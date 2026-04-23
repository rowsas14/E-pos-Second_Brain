<!--
meta:
  title: Inventory / Stocktakes / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, backend]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- freeze expected quantity snapshot at the right stage and keep post action explicit

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/inventory/features/stocktakes/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
