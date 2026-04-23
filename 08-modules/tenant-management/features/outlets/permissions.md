<!--
meta:
  title: Tenant Management / Outlets / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, permissions]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - Permissions

## Purpose
This file explains role and permission behavior for **Outlets**.

## Permission behavior
- tenant admin manages outlets
- store managers can read only the outlets they operate within

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/tenant-management/features/outlets/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/outlets/overview]] and before exposing [[api]] or [[frontend]] changes.
