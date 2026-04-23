<!--
meta:
  title: Reporting / Payment & Return Reporting / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, payment-return-reporting, data-model]
-->
> Hub: [[10-modules/reporting/features/payment-return-reporting/overview]]

# Payment & Return Reporting - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Payment & Return Reporting**.

## Primary entities
- payments
- refunds
- returns
- discount_applications

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/reporting/features/payment-return-reporting/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]

## Recommended reading order
Read after [[10-modules/reporting/features/payment-return-reporting/overview]] and [[business-rules]], then before [[application]] and [[api]].
