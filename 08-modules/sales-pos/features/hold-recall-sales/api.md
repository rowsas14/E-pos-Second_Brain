<!--
meta:
  title: Sales POS / Hold & Recall Sales / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, hold-recall-sales, api]
-->
> Hub: [[10-modules/sales-pos/features/hold-recall-sales/overview]]

# Hold & Recall Sales - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Hold & Recall Sales**.

## Endpoints / contract areas
- POST /pos/sales/{saleId}/hold
- GET /pos/sales/held
- POST /pos/sales/{saleId}/recall

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/sales-pos/features/hold-recall-sales/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/hold-recall-sales/overview]], [[business-rules]], [[data-model]], and [[application]].
