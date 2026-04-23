<!--
meta:
  title: Sales POS / Cash Movements / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, cash-movements, data-model]
-->
> Hub: [[10-modules/sales-pos/features/cash-movements/overview]]

# Cash Movements - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Cash Movements**.

## Primary entities
- cash_movement_types
- cash_movements

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/sales-pos/features/cash-movements/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/cash-movements/overview]] and [[business-rules]], then before [[application]] and [[api]].
