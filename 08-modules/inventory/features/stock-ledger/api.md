<!--
meta:
  title: Inventory / Stock Ledger / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-ledger, api]
-->
> Hub: [[10-modules/inventory/features/stock-ledger/overview]]

# Stock Ledger - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Stock Ledger**.

## Endpoints / contract areas
- GET /inventory/balances
- GET /inventory/movements
- POST /inventory/adjustments

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/inventory/features/stock-ledger/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/inventory/features/stock-transfers/overview|Stock Transfers]]
- [[10-modules/inventory/features/stocktakes/overview|Stocktakes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-ledger/overview]], [[business-rules]], [[data-model]], and [[application]].
