<!--
meta:
  title: Platform Administration / Tenant Onboarding / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, business-rules]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Tenant Onboarding** feature inside the **Platform Administration** module.

## Core rules
- tenant code must be unique
- base currency, timezone, locale, and mode must be set at creation time
- initial setup should create only tenant-owned records; platform data must stay separate
- tenant can start as pos_only, ecommerce_only, or hybrid

## Why these rules matter
The platform must onboard new retail businesses quickly without mixing platform-side setup logic with tenant staff operations.

## Related feature files
- [[10-modules/platform-administration/features/tenant-onboarding/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-onboarding/overview]], then before [[application]], [[api]], and [[validations]].
