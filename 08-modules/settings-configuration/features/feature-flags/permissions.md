<!--
meta:
  title: Settings & Configuration / Feature Flags / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, feature-flags, permissions]
-->
> Hub: [[10-modules/settings-configuration/features/feature-flags/overview]]

# Feature Flags - Permissions

## Purpose
This file explains role and permission behavior for **Feature Flags**.

## Permission behavior
- tenant admin manages tenant-owned flags
- platform may seed defaults but should not silently mutate tenant choices without policy

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/settings-configuration/features/feature-flags/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/settings-configuration/features/feature-flags/overview]] and before exposing [[api]] or [[frontend]] changes.
