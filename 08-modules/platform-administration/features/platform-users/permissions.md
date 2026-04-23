<!--
meta:
  title: Platform Administration / Platform Users / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, permissions]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - Permissions

## Purpose
This file explains role and permission behavior for **Platform Users**.

## Permission behavior
- only platform-side administrators can manage this feature
- tenant admins and store staff must never access platform-user management

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/platform-administration/features/platform-users/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/platform-users/overview]] and before exposing [[api]] or [[frontend]] changes.
