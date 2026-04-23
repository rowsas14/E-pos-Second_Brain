<!--
meta:
  title: Tenant Management / Tenants / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, application]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tenants**.

## Main orchestration paths
- view tenant profile
- update non-lifecycle tenant properties
- read tenant mode and locale during downstream setup

## Application-layer notes
- tenant resolution should be consistent across API, background job, and integration contexts
- store tenant root as shared reference in multiple modules, but never bypass same-tenant enforcement

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
