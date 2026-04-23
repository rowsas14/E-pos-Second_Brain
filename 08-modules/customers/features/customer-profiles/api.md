<!--
meta:
  title: Customers / Customer Profiles / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-profiles, api]
-->
> Hub: [[10-modules/customers/features/customer-profiles/overview]]

# Customer Profiles - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Customer Profiles**.

## Endpoints / contract areas
- POST /customers
- GET /customers
- PATCH /customers/{customerId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/customers/features/customer-profiles/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/customers/features/customer-auth/overview|Customer Auth]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-profiles/overview]], [[business-rules]], [[data-model]], and [[application]].
