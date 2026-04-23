<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, business-rules]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Deliveries** feature inside the **Fulfillment & Logistics** module.

## Core rules
- delivery belongs to one order and tenant
- delivery option type is delivery or takeaway
- line quantities are tracked at delivery-item level

## Why these rules matter
Delivery execution should be separate from order header so partial shipment remains traceable.

## Related feature files
- [[10-modules/fulfillment-logistics/features/deliveries/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/deliveries/overview]], then before [[application]], [[api]], and [[validations]].
