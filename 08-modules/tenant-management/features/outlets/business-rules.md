<!--
meta:
  title: Tenant Management / Outlets / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, business-rules]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Outlets** feature inside the **Tenant Management** module.

## Core rules
- outlet code is unique within a tenant
- outlet must belong to the same tenant as related addresses, users, tills, and inventory records
- outlet type affects stock and fulfillment behavior

## Why these rules matter
Unified commerce needs outlet-aware stock, POS execution, fulfillment assignment, and reporting.

## Related feature files
- [[10-modules/tenant-management/features/outlets/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/outlets/overview]], then before [[application]], [[api]], and [[validations]].
