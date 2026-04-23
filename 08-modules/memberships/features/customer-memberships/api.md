<!--
meta:
  title: Memberships / Customer Memberships / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [memberships, customer-memberships, api]
-->
> Hub: [[10-modules/memberships/features/customer-memberships/overview]]

# Customer Memberships - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Customer Memberships**.

## Endpoints / contract areas
- POST /customers/{customerId}/membership
- PATCH /customers/{customerId}/membership
- GET /customers/{customerId}/membership

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/memberships/features/customer-memberships/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/memberships/features/membership-tiers/overview|Membership Tiers]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/memberships/features/customer-memberships/overview]], [[business-rules]], [[data-model]], and [[application]].
