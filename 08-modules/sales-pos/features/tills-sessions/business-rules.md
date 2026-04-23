<!--
meta:
  title: Sales POS / Tills & Sessions / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, business-rules]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Tills & Sessions** feature inside the **Sales POS** module.

## Core rules
- only one open session per till
- session captures opening_float, expected_cash, counted_cash, and variance
- POS sale must belong to a till session

## Why these rules matter
POS sales, cash movements, and end-of-day reconciliation depend on clear till and session context.

## Related feature files
- [[10-modules/sales-pos/features/tills-sessions/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/tills-sessions/overview]], then before [[application]], [[api]], and [[validations]].
