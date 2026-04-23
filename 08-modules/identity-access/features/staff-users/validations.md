<!--
meta:
  title: Identity & Access / Staff Users / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, validations]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Validations

## Purpose
This file records input, business, and **workflow** validations for **Staff Users**.

## Validation rules
- reject duplicate normalized email or phone within same tenant
- block user creation without tenant context
- validate status transitions before login is allowed

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
