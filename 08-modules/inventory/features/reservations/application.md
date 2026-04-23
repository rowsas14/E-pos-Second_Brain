<!--
meta:
  title: Inventory / Reservations / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, reservations, application]
-->
> Hub: [[10-modules/inventory/features/reservations/overview]]

# Reservations - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Reservations**.

## Main orchestration paths
- reserve stock during order placement
- release reservation on cancellation or timeout
- commit reservation when fulfillment proceeds

## Application-layer notes
- reservation orchestration belongs in order placement and fulfillment services

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
