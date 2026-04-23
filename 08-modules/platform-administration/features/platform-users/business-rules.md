<!--
meta:
  title: Platform Administration / Platform Users / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, business-rules]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Platform Users** feature inside the **Platform Administration** module.

## Core rules
- platform user records must remain outside tenant-scoped users
- email must be unique at platform level
- status is limited to active, inactive, or suspended
- platform user actions must be audit-visible when they affect tenant lifecycle

## Why these rules matter
The project explicitly separates platform administration from tenant staff so platform operations do not leak into tenant authorization and reporting.

## Related feature files
- [[10-modules/platform-administration/features/platform-users/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/platform-users/overview]], then before [[application]], [[api]], and [[validations]].
