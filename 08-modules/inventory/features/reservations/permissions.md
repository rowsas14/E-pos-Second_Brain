<!--
meta:
  title: Inventory / Reservations / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, reservations, permissions]
-->
> Hub: [[10-modules/inventory/features/reservations/overview]]

# Reservations - Permissions

## Purpose
This file explains role and permission behavior for **Reservations**.

## Permission behavior
- system-driven through order workflow; manual intervention only for authorized operations staff

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/inventory/features/reservations/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/reservations/overview]] and before exposing [[api]] or [[frontend]] changes.
