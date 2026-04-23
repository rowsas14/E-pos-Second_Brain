<!--
meta:
  title: Tenant Management / Outlets / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, data-model]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Outlets**.

## Primary entities
- outlets
- outlet_types
- outlet_addresses

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/tenant-management/features/outlets/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/outlets/overview]] and [[business-rules]], then before [[application]] and [[api]].
