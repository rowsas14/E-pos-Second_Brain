<!--
meta:
  title: Reporting / Daily Sales Reporting / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, daily-sales-reporting, data-model]
-->
> Hub: [[10-modules/reporting/features/daily-sales-reporting/overview]]

# Daily Sales Reporting - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Daily Sales Reporting**.

## Primary entities
- sales
- sale_lines
- orders
- payments
- cash_movements

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/reporting/features/daily-sales-reporting/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/reporting/features/daily-sales-reporting/overview]] and [[business-rules]], then before [[application]] and [[api]].
