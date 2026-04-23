<!--
meta:
  title: Identity & Access / Outlet Assignments / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, backend]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- POS session initialization should resolve primary and allowed outlet list from assignments
- use relieved_at instead of hard delete for assignment history

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/identity-access/features/outlet-assignments/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
