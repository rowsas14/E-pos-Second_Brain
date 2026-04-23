<!--
meta:
  title: Settings & Configuration / Feature Flags / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, feature-flags, validations]
-->
> Hub: [[10-modules/settings-configuration/features/feature-flags/overview]]

# Feature Flags - Validations

## Purpose
This file records input, business, and **workflow** validations for **Feature Flags**.

## Validation rules
- validate scope-target consistency
- ensure outlet/user belongs to same tenant

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
