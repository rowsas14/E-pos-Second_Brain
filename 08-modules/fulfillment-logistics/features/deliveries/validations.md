<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, validations]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - Validations

## Purpose
This file records input, business, and **workflow** validations for **Deliveries**.

## Validation rules
- ensure delivery qty does not exceed remaining fulfillable qty
- validate order and outlet tenant consistency

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
