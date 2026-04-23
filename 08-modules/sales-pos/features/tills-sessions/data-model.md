<!--
meta:
  title: Sales POS / Tills & Sessions / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, data-model]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Tills & Sessions**.

## Primary entities
- tills
- till_sessions

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/sales-pos/features/tills-sessions/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/tills-sessions/overview]] and [[business-rules]], then before [[application]] and [[api]].
