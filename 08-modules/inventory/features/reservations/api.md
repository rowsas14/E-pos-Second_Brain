<!--
meta:
  title: Inventory / Reservations / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, reservations, api]
-->
> Hub: [[10-modules/inventory/features/reservations/overview]]

# Reservations - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Reservations**.

## Endpoints / contract areas
- GET /inventory/reservations
- POST /orders/{orderId}/reservations/release

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/inventory/features/reservations/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/reservations/overview]], [[business-rules]], [[data-model]], and [[application]].
