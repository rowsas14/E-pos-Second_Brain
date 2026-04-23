<!--
meta:
  title: Identity & Access / Outlet Assignments / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, permissions]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - Permissions

## Purpose
This file explains role and permission behavior for **Outlet Assignments**.

## Permission behavior
- tenant admin or authorized manager assigns outlet staff
- cashiers cannot self-assign outlet access

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/identity-access/features/outlet-assignments/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/identity-access/features/outlet-assignments/overview]] and before exposing [[api]] or [[frontend]] changes.
