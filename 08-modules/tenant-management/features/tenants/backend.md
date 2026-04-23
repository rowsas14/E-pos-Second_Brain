<!--
meta:
  title: Tenant Management / Tenants / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, tenants, backend]
-->
> Hub: [[10-modules/tenant-management/features/tenants/overview]]

# Tenants - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- tenant resolution should be consistent across API, background job, and integration contexts
- store tenant root as shared reference in multiple modules, but never bypass same-tenant enforcement

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/tenant-management/features/tenants/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
