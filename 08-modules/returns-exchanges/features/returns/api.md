<!--
meta:
  title: Returns & Exchanges / Returns / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, api]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Returns**.

## Endpoints / contract areas
- POST /returns
- POST /returns/{returnId}/lines
- PATCH /returns/{returnId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/returns-exchanges/features/returns/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/returns-exchanges/features/returns/overview]], [[business-rules]], [[data-model]], and [[application]].
