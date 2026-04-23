<!--
meta:
  title: Tenant Management / Tenants / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, business-rules]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Tenants** feature inside the **Tenant Management** module.

## Core rules
- every operational transaction belongs to exactly one tenant
- tenant code must be unique
- mode controls channel scope: pos_only, ecommerce_only, hybrid

## Why these rules matter
Tenant is the top ownership boundary for the unified platform. Most business and technical isolation rules depend on it.

## Related feature files
- [[10-modules/tenant-management/features/tenants/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/tenants/overview]], then before [[application]], [[api]], and [[validations]].
