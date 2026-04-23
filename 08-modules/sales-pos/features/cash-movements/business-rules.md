<!--
meta:
  title: Sales POS / Cash Movements / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, cash-movements, business-rules]
-->
> Hub: [[10-modules/sales-pos/features/cash-movements/overview]]

# Cash Movements - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Cash Movements** feature inside the **Sales POS** module.

## Core rules
- cash movement belongs to one till session
- reason is required
- movement type controls operational meaning

## Why these rules matter
Till reconciliation must include operational cash movement outside direct sale payments.

## Related feature files
- [[10-modules/sales-pos/features/cash-movements/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/cash-movements/overview]], then before [[application]], [[api]], and [[validations]].
