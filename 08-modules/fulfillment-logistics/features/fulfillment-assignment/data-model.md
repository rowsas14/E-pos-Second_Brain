<!--
meta:
  title: Fulfillment & Logistics / Fulfillment Assignment / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, fulfillment-assignment, data-model]
-->
> Hub: [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]

# Fulfillment Assignment - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Fulfillment Assignment**.

## Primary entities
- orders
- outlets
- deliveries

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]] and [[business-rules]], then before [[application]] and [[api]].
