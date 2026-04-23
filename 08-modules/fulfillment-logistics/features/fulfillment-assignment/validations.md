<!--
meta:
  title: Fulfillment & Logistics / Fulfillment Assignment / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, fulfillment-assignment, validations]
-->
> Hub: [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]

# Fulfillment Assignment - Validations

## Purpose
This file records input, business, and **workflow** validations for **Fulfillment Assignment**.

## Validation rules
- ensure outlet is eligible for fulfillment
- ensure assignment aligns with reservation/stock policy

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
