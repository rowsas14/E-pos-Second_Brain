<!--
meta:
  title: Receipts / Receipt Delivery / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, backend]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- device/integration adapters belong in infrastructure; receipt service only coordinates

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/receipts/features/receipt-delivery/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
