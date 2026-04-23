<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, validations]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - Validations

## Purpose
This file records input, business, and **workflow** validations for **Delivery Tracking**.

## Validation rules
- ensure delivery exists and belongs to tenant
- validate status progression where policy requires it

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
