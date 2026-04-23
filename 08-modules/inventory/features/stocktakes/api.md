<!--
meta:
  title: Inventory / Stocktakes / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, api]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Stocktakes**.

## Endpoints / contract areas
- POST /inventory/stocktakes
- POST /inventory/stocktakes/{stocktakeId}/lines
- POST /inventory/stocktakes/{stocktakeId}/post

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/inventory/features/stocktakes/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/inventory/features/stocktakes/overview]], [[business-rules]], [[data-model]], and [[application]].
