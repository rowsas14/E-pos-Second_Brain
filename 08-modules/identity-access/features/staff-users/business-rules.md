<!--
meta:
  title: Identity & Access / Staff Users / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, business-rules]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Staff Users** feature inside the **Identity & Access** module.

## Core rules
- each user belongs to exactly one tenant
- normalized email and phone must be unique within tenant when present
- staff user cannot be reused as platform admin identity

## Why these rules matter
The revised operating model requires every staff user to belong to exactly one tenant. This prevents cross-tenant operator leakage.

## Related feature files
- [[10-modules/identity-access/features/staff-users/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/identity-access/features/staff-users/overview]], then before [[application]], [[api]], and [[validations]].
