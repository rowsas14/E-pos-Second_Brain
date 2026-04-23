<!--
meta:
  title: Fulfillment & Logistics / Fulfillment Assignment / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, fulfillment-assignment, permissions]
-->
> Hub: [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]

# Fulfillment Assignment - Permissions

## Purpose
This file explains role and permission behavior for **Fulfillment Assignment**.

## Permission behavior
- operations staff or system automation assigns fulfillment outlet

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]] and before exposing [[api]] or [[frontend]] changes.
