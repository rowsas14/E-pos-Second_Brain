<!--
meta:
  title: Identity & Access / Staff Users / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, application]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Staff Users**.

## Main orchestration paths
- create staff user
- activate, suspend, or deactivate user
- reset staff credentials and restore access

## Application-layer notes
- keep tenant filter enforced in repository and query layer
- separate identity data from role assignment orchestration

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
