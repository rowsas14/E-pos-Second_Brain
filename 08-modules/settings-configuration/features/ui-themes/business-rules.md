<!--
meta:
  title: Settings & Configuration / UI Themes / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, ui-themes, business-rules]
-->
> Hub: [[10-modules/settings-configuration/features/ui-themes/overview]]

# UI Themes - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **UI Themes** feature inside the **Settings & Configuration** module.

## Core rules
- theme name unique within tenant
- at most one default theme per tenant
- theme_tokens payload must map to supported design tokens

## Why these rules matter
The BRD expects tenant-specific branding without developer-side CSS edits for each customer.

## Related feature files
- [[10-modules/settings-configuration/features/ui-themes/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after [[10-modules/settings-configuration/features/ui-themes/overview]], then before [[application]], [[api]], and [[validations]].
