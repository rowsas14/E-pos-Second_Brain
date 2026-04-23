<!--
meta:
  title: Identity & Access / Roles & Permissions / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, permissions]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - Permissions

## Purpose
This file explains role and permission behavior for **Roles & Permissions**.

## Permission behavior
- tenant admin owns role definition
- security-sensitive role changes should be restricted and audited

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/identity-access/features/roles-permissions/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after [[10-modules/identity-access/features/roles-permissions/overview]] and before exposing [[api]] or [[frontend]] changes.
