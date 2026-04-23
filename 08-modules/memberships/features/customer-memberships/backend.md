<!--
meta:
  title: Memberships / Customer Memberships / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, backend]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- membership state should be optional and not block core order/sale workflows if loyalty is not enabled

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/memberships/features/customer-memberships/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
