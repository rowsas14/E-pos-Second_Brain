<!--
meta:
  title: Platform Administration / Tenant Onboarding / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, application]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tenant Onboarding**.

## Main orchestration paths
- create tenant shell
- set base configuration and default theme/settings
- create first outlet and admin assignment handoff

## Application-layer notes
- use a transaction boundary for tenant root, defaults, and initial theme/settings
- raise onboarding domain events for downstream provisioning
- keep onboarding orchestration in application layer, not controller

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
