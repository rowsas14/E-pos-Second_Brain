<!--
meta:
  title: Identity & Access / Staff Users / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, edge-cases]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Staff Users**.

## Edge cases
- same email exists in different tenants
- staff user loses all outlet assignments but still has tenant-level access

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/identity-access/features/staff-users/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
