<!--
meta:
  title: Sales POS / Cash Movements / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, cash-movements, api]
-->
> Hub: [[10-modules/sales-pos/features/cash-movements/overview]]

# Cash Movements - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Cash Movements**.

## Endpoints / contract areas
- POST /pos/sessions/{sessionId}/cash-movements
- GET /pos/sessions/{sessionId}/cash-movements

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/sales-pos/features/cash-movements/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/cash-movements/overview]], [[business-rules]], [[data-model]], and [[application]].
