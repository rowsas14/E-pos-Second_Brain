<!--
meta:
  title: Identity & Access / Roles & Permissions / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, business-rules]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Roles & Permissions** feature inside the **Identity & Access** module.

## Core rules
- role scope is limited to tenant or outlet
- permission code is system-wide unique
- tenant user role assignments must stay within the same tenant

## Why these rules matter
POS discounts, refunds, stock adjustments, and administration all need explicit permission control rather than informal UI hiding.

## Related feature files
- [[10-modules/identity-access/features/roles-permissions/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after [[10-modules/identity-access/features/roles-permissions/overview]], then before [[application]], [[api]], and [[validations]].
