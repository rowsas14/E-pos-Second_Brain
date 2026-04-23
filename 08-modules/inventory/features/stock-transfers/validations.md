<!--
meta:
  title: Inventory / Stock Transfers / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, validations]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - Validations

## Purpose
This file records input, business, and **workflow** validations for **Stock Transfers**.

## Validation rules
- prevent transfer from outlet to itself
- validate requested, shipped, and received quantity consistency
- ensure transfer lines reference valid tenant variant

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
