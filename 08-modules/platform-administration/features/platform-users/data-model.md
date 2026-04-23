<!--
meta:
  title: Platform Administration / Platform Users / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, data-model]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Platform Users**.

## Primary entities
- platform_users

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/platform-administration/features/platform-users/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/platform-users/overview]] and [[business-rules]], then before [[application]] and [[api]].
