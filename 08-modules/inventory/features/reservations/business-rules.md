<!--
meta:
  title: Inventory / Reservations / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, reservations, business-rules]
-->
> Hub: [[10-modules/inventory/features/reservations/overview]]

# Reservations - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Reservations** feature inside the **Inventory** module.

## Core rules
- reservation belongs to tenant, outlet, variant, and order
- status moves through active, released, committed, or expired
- reserved quantity contributes to available_qty reduction

## Why these rules matter
Online checkout needs to protect sellable stock before shipment while still allowing later release or commitment.

## Related feature files
- [[10-modules/inventory/features/reservations/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/reservations/overview]], then before [[application]], [[api]], and [[validations]].
