<!--
meta:
  title: Fulfillment & Logistics / Deliveries / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, deliveries, backend]
-->
> Hub: [[10-modules/fulfillment-logistics/features/deliveries/overview]]

# Deliveries - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- fulfillment module should update order item fulfilled_qty through controlled services

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/fulfillment-logistics/features/deliveries/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview|Delivery Tracking]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
