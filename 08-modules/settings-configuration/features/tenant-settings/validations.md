<!--
meta:
  title: Settings & Configuration / Tenant Settings / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, tenant-settings, validations]
-->
> Hub: [[10-modules/settings-configuration/features/tenant-settings/overview]]

# Tenant Settings - Validations

## Purpose
This file records input, business, and **workflow** validations for **Tenant Settings**.

## Validation rules
- ensure exactly one scope target is set according to scope
- validate channel value when scope is channel

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/settings-configuration/features/feature-flags/overview|Feature Flags]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
