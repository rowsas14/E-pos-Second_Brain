<!--
meta:
  title: Inventory / Stocktakes / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stocktakes, application]
-->
> Hub: [[10-modules/inventory/features/stocktakes/overview]]

# Stocktakes - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Stocktakes**.

## Main orchestration paths
- open count session
- capture line counts
- post variance adjustments

## Application-layer notes
- freeze expected quantity snapshot at the right stage and keep post action explicit

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
