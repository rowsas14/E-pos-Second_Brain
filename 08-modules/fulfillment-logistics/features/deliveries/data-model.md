<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, data-model]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Deliveries**.

## Primary entities
- deliveries
- delivery_items
- delivery_option_types

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/fulfillment-logistics/features/deliveries/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/deliveries/overview]] and [[business-rules]], then before [[application]] and [[api]].
