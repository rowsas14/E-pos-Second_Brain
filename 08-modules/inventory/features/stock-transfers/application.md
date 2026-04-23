<!--
meta:
  title: Inventory / Stock Transfers / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, application]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Stock Transfers**.

## Main orchestration paths
- request transfer
- approve and ship transfer
- receive transfer and post final stock movement

## Application-layer notes
- treat shipment and receipt as distinct transaction points

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
