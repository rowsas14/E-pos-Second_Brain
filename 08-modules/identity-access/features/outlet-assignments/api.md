<!--
meta:
  title: Identity & Access / Outlet Assignments / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, outlet-assignments, api]
-->
> Hub: [[10-modules/identity-access/features/outlet-assignments/overview]]

# Outlet Assignments - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Outlet Assignments**.

## Endpoints / contract areas
- POST /outlets/{outletId}/user-roles
- PATCH /outlets/{outletId}/user-roles/{assignmentId}
- DELETE /outlets/{outletId}/user-roles/{assignmentId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/identity-access/features/outlet-assignments/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/identity-access/features/outlet-assignments/overview]], [[business-rules]], [[data-model]], and [[application]].
