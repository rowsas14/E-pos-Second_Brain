<!--
meta:
  title: Identity & Access / Roles & Permissions / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, application]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Roles & Permissions**.

## Main orchestration paths
- create tenant role
- attach permission set to role
- assign tenant-scoped role to user

## Application-layer notes
- keep authorization policy evaluation separate from role maintenance APIs
- cache permission resolution carefully and invalidate on assignment changes

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
