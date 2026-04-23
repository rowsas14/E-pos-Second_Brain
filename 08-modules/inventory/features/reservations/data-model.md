<!--
meta:
  title: Inventory / Reservations / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, reservations, data-model]
-->
> Hub: [[10-modules/inventory/features/reservations/overview]]

# Reservations - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Reservations**.

## Primary entities
- stock_reservations
- inventory_balances

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/inventory/features/reservations/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/reservations/overview]] and [[business-rules]], then before [[application]] and [[api]].
