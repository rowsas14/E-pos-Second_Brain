<!--
meta:
  title: Returns & Exchanges / Exchanges / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, exchanges, api]
-->
> Hub: [[10-modules/returns-exchanges/features/exchanges/overview]]

# Exchanges - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Exchanges**.

## Endpoints / contract areas
- POST /returns/{returnId}/exchange
- POST /exchanges/{exchangeId}/lines
- POST /exchanges/{exchangeId}/complete

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/returns-exchanges/features/exchanges/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[10-modules/returns-exchanges/features/exchanges/overview]], [[business-rules]], [[data-model]], and [[application]].
