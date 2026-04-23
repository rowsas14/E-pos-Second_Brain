<!--
meta:
  title: Platform Administration / Tenant Onboarding / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, permissions]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - Permissions

## Purpose
This file explains role and permission behavior for **Tenant Onboarding**.

## Permission behavior
- platform admin creates and activates onboarding records
- tenant admin receives access only after onboarding handoff

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/platform-administration/features/tenant-onboarding/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-onboarding/overview]] and before exposing [[api]] or [[frontend]] changes.
