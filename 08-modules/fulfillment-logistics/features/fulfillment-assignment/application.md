<!--
meta:
  title: Fulfillment & Logistics / Fulfillment Assignment / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, fulfillment-assignment, application]
-->
> Hub: [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]

# Fulfillment Assignment - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Fulfillment Assignment**.

## Main orchestration paths
- assign fulfillment outlet during order processing
- reassign if stock or operations change

## Application-layer notes
- assignment logic may start manual, but should be separated so automation rules can be added later

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
