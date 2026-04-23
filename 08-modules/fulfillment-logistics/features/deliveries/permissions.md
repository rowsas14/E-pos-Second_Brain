<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, permissions]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - Permissions

## Purpose
This file explains role and permission behavior for **Deliveries**.

## Permission behavior
- fulfillment staff manages delivery execution

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/fulfillment-logistics/features/deliveries/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/deliveries/overview]] and before exposing [[api]] or [[frontend]] changes.
