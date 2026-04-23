<!--
meta:
  title: Identity & Access / Outlet Assignments / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, application]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Outlet Assignments**.

## Main orchestration paths
- assign user to outlet
- mark primary outlet
- relieve or transfer staff between outlets

## Application-layer notes
- POS session initialization should resolve primary and allowed outlet list from assignments
- use relieved_at instead of hard delete for assignment history

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
