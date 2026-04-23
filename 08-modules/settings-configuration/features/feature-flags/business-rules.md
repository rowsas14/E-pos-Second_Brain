<!--
meta:
  title: Settings & Configuration / Feature Flags / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, feature-flags, business-rules]
-->
> Hub: [[10-modules/settings-configuration/features/feature-flags/overview]]

# Feature Flags - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Feature Flags** feature inside the **Settings & Configuration** module.

## Core rules
- scope is tenant, outlet, or user
- exactly one scope target must match the scope field
- flags should never be used to bypass tenant isolation rules

## Why these rules matter
Gradual rollout and tenant-specific capability control are required for a multi-tenant platform.

## Related feature files
- [[10-modules/settings-configuration/features/feature-flags/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/settings-configuration/features/feature-flags/overview]], then before [[application]], [[api]], and [[validations]].
