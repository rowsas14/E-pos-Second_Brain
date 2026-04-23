<!--
meta:
  title: Identity & Access / Outlet Assignments / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, business-rules]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Outlet Assignments** feature inside the **Identity & Access** module.

## Core rules
- user, outlet, role, and tenant must match
- assigned role must have outlet scope
- employee_code, when used, must be unique per outlet among active assignments

## Why these rules matter
Cashiers and outlet staff need operational access tied to the correct store or warehouse, not just tenant-wide identity.

## Related feature files
- [[10-modules/identity-access/features/outlet-assignments/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/identity-access/features/outlet-assignments/overview]], then before [[application]], [[api]], and [[validations]].
