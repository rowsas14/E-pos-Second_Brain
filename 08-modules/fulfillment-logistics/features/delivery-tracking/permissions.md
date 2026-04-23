<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, permissions]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - Permissions

## Purpose
This file explains role and permission behavior for **Delivery Tracking**.

## Permission behavior
- system and fulfillment staff write events
- customer can read tenant-approved shipment progress

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]] and before exposing [[api]] or [[frontend]] changes.
