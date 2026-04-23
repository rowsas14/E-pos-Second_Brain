<!--
meta:
  title: Platform Administration / Platform Users / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, validations]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - Validations

## Purpose
This file records input, business, and **workflow** validations for **Platform Users**.

## Validation rules
- reject duplicate platform email
- block suspension of the last recoverable active platform account without explicit override
- enforce password and session controls separately from tenant auth

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
