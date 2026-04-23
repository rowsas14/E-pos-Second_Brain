<!--
meta:
  title: Orders E-Commerce / Orders / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, orders, business-rules]
-->
> Hub: [[10-modules/orders-ecommerce/features/orders/overview]]

# Orders - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Orders** feature inside the **Orders E-Commerce** module.

## Core rules
- order number unique within tenant
- order uses address snapshots, not mutable customer address references
- fulfillment and payment status are tracked separately from order status

## Why these rules matter
Orders are the commercial commitment point for online channel operations.

## Related feature files
- [[10-modules/orders-ecommerce/features/orders/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/orders-ecommerce/features/carts/overview|Carts]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/orders/overview]], then before [[application]], [[api]], and [[validations]].
