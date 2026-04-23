<!--
meta:
  title: Memberships / Membership Tiers / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, backend]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- keep tier logic simple until advanced loyalty rules are introduced

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/memberships/features/membership-tiers/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
