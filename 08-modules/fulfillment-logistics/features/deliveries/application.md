<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, application]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Deliveries**.

## Main orchestration paths
- create delivery
- assign order items/quantities
- mark packed, shipped, delivered, or returned

## Application-layer notes
- fulfillment module should update order item fulfilled_qty through controlled services

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
