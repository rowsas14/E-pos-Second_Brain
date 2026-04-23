<!--
meta:
  title: Fulfillment & Logistics / Fulfillment Assignment / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, fulfillment-assignment, business-rules]
-->
> Hub: [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]

# Fulfillment Assignment - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Fulfillment Assignment** feature inside the **Fulfillment & Logistics** module.

## Core rules
- fulfillment outlet must belong to the same tenant
- assignment should consider outlet type and stock availability

## Why these rules matter
The schema allows fulfillment_outlet_id because online orders may be served from different locations.

## Related feature files
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]], then before [[application]], [[api]], and [[validations]].
