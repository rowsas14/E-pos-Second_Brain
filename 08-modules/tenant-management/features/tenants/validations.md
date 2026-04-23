<!--
meta:
  title: Tenant Management / Tenants / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, validations]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Validations

## Purpose
This file records input, business, and **workflow** validations for **Tenants**.

## Validation rules
- validate currency, locale, timezone, and code format
- reject unsupported mode transition without impact review

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
