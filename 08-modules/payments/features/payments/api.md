<!--
meta:
  title: Payments / Payments / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, api]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Payments**.

## Endpoints / contract areas
- POST /payments
- GET /payments/{paymentId}
- PATCH /payments/{paymentId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/payments/features/payments/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[10-modules/payments/features/payments/overview]], [[business-rules]], [[data-model]], and [[application]].
