<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, api]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Delivery Tracking**.

## Endpoints / contract areas
- POST /deliveries/{deliveryId}/tracking-events
- GET /deliveries/{deliveryId}/tracking

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]], [[business-rules]], [[data-model]], and [[application]].
