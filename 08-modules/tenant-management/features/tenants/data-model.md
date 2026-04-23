<!--
meta:
  title: Tenant Management / Tenants / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, data-model]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Tenants**.

## Primary entities
- tenants

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/tenant-management/features/tenants/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/tenants/overview]] and [[business-rules]], then before [[application]] and [[api]].
