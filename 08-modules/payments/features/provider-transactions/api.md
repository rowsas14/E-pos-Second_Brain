<!--
meta:
  title: Payments / Provider Transactions / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, api]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Provider Transactions**.

## Endpoints / contract areas
- POST /payments/providers/{providerCode}/webhooks
- GET /payments/{paymentId}/transactions

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/payments/features/provider-transactions/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[10-modules/payments/features/provider-transactions/overview]], [[business-rules]], [[data-model]], and [[application]].
