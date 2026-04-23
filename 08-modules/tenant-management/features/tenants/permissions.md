<!--
meta:
  title: Tenant Management / Tenants / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, permissions]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Permissions

## Purpose
This file explains role and permission behavior for **Tenants**.

## Permission behavior
- platform admin creates tenant
- tenant admin manages tenant-owned settings but not platform lifecycle

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/tenant-management/features/tenants/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/tenants/overview]] and before exposing [[api]] or [[frontend]] changes.
