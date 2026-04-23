<!--
meta:
  title: Settings & Configuration / Tenant Settings / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, tenant-settings, application]
-->
> Hub: [[10-modules/settings-configuration/features/tenant-settings/overview]]

# Tenant Settings - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Tenant Settings**.

## Main orchestration paths
- create or update setting
- resolve setting at runtime by scope precedence

## Application-layer notes
- use typed setting accessors in application layer instead of scattering raw JSON parsing everywhere

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/settings-configuration/features/feature-flags/overview|Feature Flags]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
