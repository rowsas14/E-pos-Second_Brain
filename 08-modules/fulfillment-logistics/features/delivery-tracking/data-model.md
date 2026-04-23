<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, data-model]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Delivery Tracking**.

## Primary entities
- delivery_tracking

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]] and [[business-rules]], then before [[application]] and [[api]].
