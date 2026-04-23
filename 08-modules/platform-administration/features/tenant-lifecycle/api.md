<!--
meta:
  title: Platform Administration / Tenant Lifecycle / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, tenant-lifecycle, api]
-->
> Hub: [[10-modules/platform-administration/features/tenant-lifecycle/overview]]

# Tenant Lifecycle - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Tenant Lifecycle**.

## Endpoints / contract areas
- PATCH /platform/tenants/{tenantId}/status
- GET /platform/tenants/{tenantId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/platform-administration/features/tenant-lifecycle/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/tenant-lifecycle/overview]], [[business-rules]], [[data-model]], and [[application]].
