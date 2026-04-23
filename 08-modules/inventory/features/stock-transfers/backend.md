<!--
meta:
  title: Inventory / Stock Transfers / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, backend]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- treat shipment and receipt as distinct transaction points

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/inventory/features/stock-transfers/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
