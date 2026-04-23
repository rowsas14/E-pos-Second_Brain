<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, business-rules]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Delivery Tracking** feature inside the **Fulfillment & Logistics** module.

## Core rules
- tracking event belongs to one delivery
- event_time is required
- payload may store carrier raw data

## Why these rules matter
Customers and ops staff need a clear timeline beyond only current delivery status.

## Related feature files
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]], then before [[application]], [[api]], and [[validations]].
