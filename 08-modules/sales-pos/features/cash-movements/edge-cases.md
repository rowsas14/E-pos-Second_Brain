<!--
meta:
  title: Sales POS / Cash Movements / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, cash-movements, edge-cases]
-->
> Hub: [[10-modules/sales-pos/features/cash-movements/overview]]

# Cash Movements - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Cash Movements**.

## Edge cases
- cash movement recorded near close time but not included in expected cash calculation

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/sales-pos/features/cash-movements/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
