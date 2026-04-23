<!--
meta:
  title: Sales POS / Cash Movements / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, cash-movements, application]
-->
> Hub: [[10-modules/sales-pos/features/cash-movements/overview]]

# Cash Movements - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Cash Movements**.

## Main orchestration paths
- record cash in/out
- perform safe drop
- review cash events during register close

## Application-layer notes
- reconciliation service should include cash movements when computing expected cash

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/reporting/features/daily-sales-reporting/overview|Daily Sales Reporting]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
