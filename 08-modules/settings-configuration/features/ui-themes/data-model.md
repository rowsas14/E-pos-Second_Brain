<!--
meta:
  title: Settings & Configuration / UI Themes / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, ui-themes, data-model]
-->
> Hub: [[10-modules/settings-configuration/features/ui-themes/overview]]

# UI Themes - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **UI Themes**.

## Primary entities
- ui_themes

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/settings-configuration/features/ui-themes/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after [[10-modules/settings-configuration/features/ui-themes/overview]] and [[business-rules]], then before [[application]] and [[api]].
