<!--
meta:
  title: Identity & Access / Staff Users / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, backend]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- keep tenant filter enforced in repository and query layer
- separate identity data from role assignment orchestration

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/identity-access/features/staff-users/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
