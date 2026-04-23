<!--
meta:
  title: Sales POS / Cash Movements / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, cash-movements, validations]
-->
> Hub: [[10-modules/sales-pos/features/cash-movements/overview]]

# Cash Movements - Validations

## Purpose
This file records input, business, and **workflow** validations for **Cash Movements**.

## Validation rules
- block cash movement without open session
- validate amount is positive

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
