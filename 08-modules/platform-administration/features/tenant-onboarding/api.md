<!--
meta:
  title: Platform Administration / Tenant Onboarding / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-onboarding, api]
-->
> Hub: [[10-modules/platform-administration/features/tenant-onboarding/overview]]

# Tenant Onboarding - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Tenant Onboarding**.

## Endpoints / contract areas
- POST /platform/tenants
- POST /platform/tenants/{tenantId}/bootstrap
- POST /platform/tenants/{tenantId}/handoff

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/platform-administration/features/tenant-onboarding/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/tenants/overview|Tenants]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-onboarding/overview]], [[business-rules]], [[data-model]], and [[application]].
