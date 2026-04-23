<!--
meta:
  title: Customers / Customer Addresses / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-addresses, api]
-->
> Hub: [[10-modules/customers/features/customer-addresses/overview]]

# Customer Addresses - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Customer Addresses**.

## Endpoints / contract areas
- POST /customers/{customerId}/addresses
- PATCH /customers/{customerId}/addresses/{addressId}
- DELETE /customers/{customerId}/addresses/{addressId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/customers/features/customer-addresses/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-addresses/overview]], [[business-rules]], [[data-model]], and [[application]].
