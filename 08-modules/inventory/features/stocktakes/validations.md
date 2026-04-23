<!--
meta:
  title: Inventory / Stocktakes / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, validations]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Validations

## Purpose
This file records input, business, and **workflow** validations for **Stocktakes**.

## Validation rules
- prevent posting twice
- ensure each variant appears once per stocktake
- validate counted quantities before posting

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
