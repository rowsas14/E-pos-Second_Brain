<!--
meta:
  title: Customers / Customer Profiles / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, backend]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- customer merge strategy, if ever needed, must remain tenant-scoped

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/customers/features/customer-profiles/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
