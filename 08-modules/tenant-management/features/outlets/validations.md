<!--
meta:
  title: Tenant Management / Outlets / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, validations]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - Validations

## Purpose
This file records input, business, and **workflow** validations for **Outlets**.

## Validation rules
- reject duplicate outlet code within tenant
- ensure address and outlet tenant_id match
- validate timezone and outlet type before activation

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
