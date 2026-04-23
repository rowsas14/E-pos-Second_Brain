<!--
meta:
  title: Tenant Management / Outlets / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, application]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Outlets**.

## Main orchestration paths
- create outlet
- assign outlet type and address
- activate/deactivate outlet for operations

## Application-layer notes
- outlet should be referenced by inventory, till, order fulfillment, and staff assignment services
- use outlet type to drive allowed workflows rather than UI assumptions

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
