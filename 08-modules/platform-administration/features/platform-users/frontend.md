<!--
meta:
  title: Platform Administration / Platform Users / Frontend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, frontend]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - Frontend

## Purpose
This file captures **frontend** behavior, screens, and UI integration points for **Platform Users**.

## Frontend behavior notes
- internal back-office screens only; no tenant-facing UI
- platform user list, status toggle, and access recovery screens
- must be visually separated from tenant admin user management

## Frontend dependency map
- [[10-modules/platform-administration/features/platform-users/overview]] for scope
- [[workflows]] for user flow
- [[permissions]] for access behavior
- [[api]] for contract usage
- [[edge-cases]] for failure state design

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/platform-users/overview]], [[workflows]], [[permissions]], and [[api]].
