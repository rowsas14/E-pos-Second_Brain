<!--
meta:
  title: Identity & Access / Outlet Assignments / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, edge-cases]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Outlet Assignments**.

## Edge cases
- user has multiple active outlet assignments
- primary outlet removed while user still has open session at that outlet

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/identity-access/features/outlet-assignments/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
