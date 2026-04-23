<!--
meta:
  title: Settings & Configuration / Feature Flags / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, feature-flags, application]
-->
> Hub: [[10-modules/settings-configuration/features/feature-flags/overview]]

# Feature Flags - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Feature Flags**.

## Main orchestration paths
- enable feature for tenant
- enable pilot feature for one outlet or user
- read resolved flag during runtime

## Application-layer notes
- feature flag resolver should be centralized and side-effect free

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
