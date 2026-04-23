<!--
meta:
  title: Tax / Tax Classes / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, backend]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- tax class lookup should be lightweight but cached carefully

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/tax/features/tax-classes/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
