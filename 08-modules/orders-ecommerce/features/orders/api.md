<!--
meta:
  title: Orders E-Commerce / Orders / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, orders, api]
-->
> Hub: [[10-modules/orders-ecommerce/features/orders/overview]]

# Orders - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Orders**.

## Endpoints / contract areas
- POST /store/orders
- GET /store/orders/{orderId}
- PATCH /orders/{orderId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/orders-ecommerce/features/orders/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/carts/overview|Carts]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/orders/overview]], [[business-rules]], [[data-model]], and [[application]].
