<!--
meta:
  title: Identity & Access / Roles & Permissions / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [identity-access, roles-permissions, api]
-->
> Hub: [[10-modules/identity-access/features/roles-permissions/overview]]

# Roles & Permissions - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Roles & Permissions**.

## Endpoints / contract areas
- POST /roles
- POST /roles/{roleId}/permissions
- POST /users/{userId}/tenant-roles

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/identity-access/features/roles-permissions/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/identity-access/features/staff-users/overview|Staff Users]]
- [[10-modules/identity-access/features/outlet-assignments/overview|Outlet Assignments]]
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]

## Recommended reading order
Read after [[10-modules/identity-access/features/roles-permissions/overview]], [[business-rules]], [[data-model]], and [[application]].
