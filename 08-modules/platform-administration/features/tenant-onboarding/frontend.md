<!--
meta:
  title: Platform Administration / Tenant Onboarding / Frontend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, frontend]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - Frontend

## Purpose
This file captures **frontend** behavior, screens, and UI integration points for **Tenant Onboarding**.

## Frontend behavior notes
- platform onboarding wizard with step-by-step configuration
- show channel mode, locale, timezone, and initial outlet setup in one controlled flow
- surface incomplete onboarding state clearly

## Frontend dependency map
- [[10-modules/platform-administration/features/tenant-onboarding/overview]] for scope
- [[workflows]] for user flow
- [[permissions]] for access behavior
- [[api]] for contract usage
- [[edge-cases]] for failure state design

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-onboarding/overview]], [[workflows]], [[permissions]], and [[api]].
