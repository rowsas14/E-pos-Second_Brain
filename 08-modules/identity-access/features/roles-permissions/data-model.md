<!--
meta:
  title: Identity & Access / Roles & Permissions / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, data-model]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Roles & Permissions**.

## Primary entities
- roles
- permissions
- role_permissions
- tenant_user_roles

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/identity-access/features/roles-permissions/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after [[10-modules/identity-access/features/roles-permissions/overview]] and [[business-rules]], then before [[application]] and [[api]].
