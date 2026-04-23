<!--
meta:
  title: Identity & Access / Staff Users / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, data-model]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Staff Users**.

## Primary entities
- users

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/identity-access/features/staff-users/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/identity-access/features/staff-users/overview]] and [[business-rules]], then before [[application]] and [[api]].
