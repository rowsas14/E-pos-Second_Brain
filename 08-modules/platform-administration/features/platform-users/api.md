<!--
meta:
  title: Platform Administration / Platform Users / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [platform-administration, platform-users, api]
-->
> Hub: [[10-modules/platform-administration/features/platform-users/overview]]

# Platform Users - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Platform Users**.

## Endpoints / contract areas
- POST /platform/users
- GET /platform/users
- PATCH /platform/users/{platformUserId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/platform-administration/features/platform-users/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/platform-administration/features/tenant-onboarding/overview|Tenant Onboarding]]
- [[10-modules/platform-administration/features/tenant-lifecycle/overview|Tenant Lifecycle]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/platform-administration/features/platform-users/overview]], [[business-rules]], [[data-model]], and [[application]].
