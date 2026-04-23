<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, api]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Deliveries**.

## Endpoints / contract areas
- POST /orders/{orderId}/deliveries
- PATCH /deliveries/{deliveryId}/status
- POST /deliveries/{deliveryId}/items

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/fulfillment-logistics/features/deliveries/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/deliveries/overview]], [[business-rules]], [[data-model]], and [[application]].
