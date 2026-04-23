<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, backend]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- tracking ingestion should be append-only and resilient to duplicate events

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
