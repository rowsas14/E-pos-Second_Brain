<!--
meta:
  title: Settings & Configuration / UI Themes / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, ui-themes, application]
-->
> Hub: [[10-modules/settings-configuration/features/ui-themes/overview]]

# UI Themes - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **UI Themes**.

## Main orchestration paths
- create theme
- set default theme
- preview and apply branding

## Application-layer notes
- theme storage is configuration; rendering layer should consume normalized tokens, not raw ad-hoc CSS fragments

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
