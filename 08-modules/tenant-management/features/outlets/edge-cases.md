<!--
meta:
  title: Tenant Management / Outlets / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, edge-cases]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Outlets**.

## Edge cases
- outlet deactivated while stock or till session is open
- warehouse outlet used incorrectly as POS billing location

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/tenant-management/features/outlets/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
