<!--
meta:
  title: Reporting / Daily Sales Reporting / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, daily-sales-reporting, application]
-->
> Hub: [[10-modules/reporting/features/daily-sales-reporting/overview]]

# Daily Sales Reporting - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Daily Sales Reporting**.

## Main orchestration paths
- view daily sales dashboard
- filter by outlet and channel
- export summary

## Application-layer notes
- read models or optimized queries may be needed; do not let reporting logic leak into transactional services

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
