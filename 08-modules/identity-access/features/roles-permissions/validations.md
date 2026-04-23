<!--
meta:
  title: Identity & Access / Roles & Permissions / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, validations]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - Validations

## Purpose
This file records input, business, and **workflow** validations for **Roles & Permissions**.

## Validation rules
- reject outlet-scoped role assignment in tenant_user_roles
- reject duplicate role code within tenant
- ensure permission ids are valid and active before mapping

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
