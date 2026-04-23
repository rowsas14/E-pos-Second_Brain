<!--
meta:
  title: Identity & Access / Staff Users / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, permissions]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Permissions

## Purpose
This file explains role and permission behavior for **Staff Users**.

## Permission behavior
- tenant admin manages staff master data
- managers may view but not fully administer all staff records unless granted permission

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/identity-access/features/staff-users/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/identity-access/features/staff-users/overview]] and before exposing [[api]] or [[frontend]] changes.
