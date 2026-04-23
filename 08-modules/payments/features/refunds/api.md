<!--
meta:
  title: Payments / Refunds / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, api]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Refunds**.

## Endpoints / contract areas
- POST /refunds
- GET /refunds/{refundId}
- PATCH /refunds/{refundId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/payments/features/refunds/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/refunds/overview]], [[business-rules]], [[data-model]], and [[application]].
