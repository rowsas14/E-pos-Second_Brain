<!--
meta:
  title: Inventory / Stocktakes / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, business-rules]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Stocktakes** feature inside the **Inventory** module.

## Core rules
- status moves through draft, counting, posted, cancelled
- line delta determines gain or loss movement on posting
- stocktake is outlet-scoped

## Why these rules matter
Retail operations need controlled stock reconciliation without directly editing balances.

## Related feature files
- [[10-modules/inventory/features/stocktakes/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/inventory/features/stocktakes/overview]], then before [[application]], [[api]], and [[validations]].
