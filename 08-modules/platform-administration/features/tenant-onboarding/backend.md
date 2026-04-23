<!--
meta:
  title: Platform Administration / Tenant Onboarding / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, backend]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- use a transaction boundary for tenant root, defaults, and initial theme/settings
- raise onboarding domain events for downstream provisioning
- keep onboarding orchestration in application layer, not controller

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/platform-administration/features/tenant-onboarding/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
