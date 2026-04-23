<!--
meta:
  title: Orders E-Commerce / Orders / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, orders, permissions]
-->
> Hub: [[10-modules/orders-ecommerce/features/orders/overview]]

# Orders - Permissions

## Purpose
This file explains role and permission behavior for **Orders**.

## Permission behavior
- customer places order
- ops/admin staff manage lifecycle after placement

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/orders-ecommerce/features/orders/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/carts/overview|Carts]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/orders/overview]] and before exposing [[api]] or [[frontend]] changes.
