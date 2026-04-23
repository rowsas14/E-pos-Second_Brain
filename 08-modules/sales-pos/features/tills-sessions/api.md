<!--
meta:
  title: Sales POS / Tills & Sessions / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, api]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Tills & Sessions**.

## Endpoints / contract areas
- POST /pos/tills/{tillId}/sessions/open
- POST /pos/sessions/{sessionId}/close
- GET /pos/sessions/current

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/sales-pos/features/tills-sessions/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/tills-sessions/overview]], [[business-rules]], [[data-model]], and [[application]].
