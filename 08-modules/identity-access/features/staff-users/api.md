<!--
meta:
  title: Identity & Access / Staff Users / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, staff-users, api]
-->
> Hub: [[10-modules/identity-access/features/staff-users/overview]]

# Staff Users - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Staff Users**.

## Endpoints / contract areas
- POST /users
- GET /users
- PATCH /users/{userId}
- PATCH /users/{userId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/identity-access/features/staff-users/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/identity-access/features/roles-permissions/overview|Roles & Permissions]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/audit-compliance/features/audit-logs/overview|Audit Logs]]

## Recommended reading order
Read after [[10-modules/identity-access/features/staff-users/overview]], [[business-rules]], [[data-model]], and [[application]].
