<!--
meta:
  title: Customers / Customer Auth / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-auth, api]
-->
> Hub: [[10-modules/customers/features/customer-auth/overview]]

# Customer Auth - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Customer Auth**.

## Endpoints / contract areas
- POST /auth/customers/register
- POST /auth/customers/login
- POST /auth/customers/identities/link

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/customers/features/customer-auth/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-auth/overview]], [[business-rules]], [[data-model]], and [[application]].
