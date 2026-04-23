<!--
meta:
  title: Inventory / Stock Transfers / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, edge-cases]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Stock Transfers**.

## Edge cases
- partial receipt
- cancel transfer after shipment already happened

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/inventory/features/stock-transfers/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
