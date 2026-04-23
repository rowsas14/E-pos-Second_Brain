<!--
meta:
  title: Inventory / Reservations / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, reservations, validations]
-->
> Hub: [[10-modules/inventory/features/reservations/overview]]

# Reservations - Validations

## Purpose
This file records input, business, and **workflow** validations for **Reservations**.

## Validation rules
- reject reservation beyond available policy
- ensure order and reservation tenant match
- validate release/commit against current status

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
