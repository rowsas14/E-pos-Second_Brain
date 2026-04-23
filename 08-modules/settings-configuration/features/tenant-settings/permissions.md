<!--
meta:
  title: Settings & Configuration / Tenant Settings / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, tenant-settings, permissions]
-->
> Hub: [[10-modules/settings-configuration/features/tenant-settings/overview]]

# Tenant Settings - Permissions

## Purpose
This file explains role and permission behavior for **Tenant Settings**.

## Permission behavior
- tenant admin manages settings

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/settings-configuration/features/tenant-settings/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/settings-configuration/features/feature-flags/overview|Feature Flags]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after [[10-modules/settings-configuration/features/tenant-settings/overview]] and before exposing [[api]] or [[frontend]] changes.
