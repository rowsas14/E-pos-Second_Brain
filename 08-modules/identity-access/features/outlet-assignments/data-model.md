<!--
meta:
  title: Identity & Access / Outlet Assignments / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, data-model]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Outlet Assignments**.

## Primary entities
- outlet_user_roles

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/identity-access/features/outlet-assignments/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/identity-access/features/outlet-assignments/overview]] and [[business-rules]], then before [[application]] and [[api]].
