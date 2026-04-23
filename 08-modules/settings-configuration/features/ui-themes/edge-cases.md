<!--
meta:
  title: Settings & Configuration / UI Themes / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, ui-themes, edge-cases]
-->
> Hub: [[10-modules/settings-configuration/features/ui-themes/overview]]

# UI Themes - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **UI Themes**.

## Edge cases
- theme changed while cashier session is active
- storefront and admin consuming different token versions

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/settings-configuration/features/ui-themes/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
