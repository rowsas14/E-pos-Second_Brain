<!--
meta:
  title: Platform Administration / Platform Users / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, application]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Platform Users**.

## Main orchestration paths
- create platform admin identity
- sign in to internal control area
- suspend or reactivate internal operator access

## Application-layer notes
- keep PlatformUser aggregate and repository separate from tenant Users
- use dedicated platform auth middleware/policy
- store security and last_login_at in platform schema scope

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
