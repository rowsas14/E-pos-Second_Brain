<!--
meta:
  title: Identity & Access / Roles & Permissions / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, edge-cases]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Roles & Permissions**.

## Edge cases
- role edited after users already depend on it
- permission removed while an approval workflow is in progress

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/identity-access/features/roles-permissions/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
