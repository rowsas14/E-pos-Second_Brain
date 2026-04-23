<!--
meta:
  title: Platform Administration / Tenant Onboarding / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, data-model]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Tenant Onboarding**.

## Primary entities
- tenants
- outlets
- tenant_settings
- ui_themes
- feature_flags

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/platform-administration/features/tenant-onboarding/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-onboarding/overview]] and [[business-rules]], then before [[application]] and [[api]].
