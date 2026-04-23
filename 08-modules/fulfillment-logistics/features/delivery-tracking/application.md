<!--
meta:
  title: Fulfillment & Logistics / Delivery Tracking / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, delivery-tracking, application]
-->
> Hub: [[10-modules/fulfillment-logistics/features/delivery-tracking/overview]]

# Delivery Tracking - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Delivery Tracking**.

## Main orchestration paths
- append internal tracking event
- ingest carrier update
- display tracking timeline

## Application-layer notes
- tracking ingestion should be append-only and resilient to duplicate events

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
