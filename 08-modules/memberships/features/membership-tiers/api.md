<!--
meta:
  title: Memberships / Membership Tiers / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, membership-tiers, api]
-->
> Hub: [[10-modules/memberships/features/membership-tiers/overview]]

# Membership Tiers - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Membership Tiers**.

## Endpoints / contract areas
- POST /memberships/tiers
- PATCH /memberships/tiers/{tierId}
- GET /memberships/tiers

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/memberships/features/membership-tiers/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/memberships/features/membership-tiers/overview]], [[business-rules]], [[data-model]], and [[application]].
