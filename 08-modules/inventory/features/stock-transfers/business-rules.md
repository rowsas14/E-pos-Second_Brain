<!--
meta:
  title: Inventory / Stock Transfers / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, business-rules]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Stock Transfers** feature inside the **Inventory** module.

## Core rules
- transfer status moves through draft, approved, in_transit, received, cancelled
- source and destination outlets must belong to same tenant
- shipment and receipt quantities are tracked separately

## Why these rules matter
Unified commerce needs stock repositioning between store and fulfillment locations without breaking auditability.

## Related feature files
- [[10-modules/inventory/features/stock-transfers/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-transfers/overview]], then before [[application]], [[api]], and [[validations]].
