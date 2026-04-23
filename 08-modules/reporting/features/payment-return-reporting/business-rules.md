<!--
meta:
  title: Reporting / Payment & Return Reporting / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, payment-return-reporting, business-rules]
-->
> Hub: [[10-modules/reporting/features/payment-return-reporting/overview]]

# Payment & Return Reporting - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Payment & Return Reporting** feature inside the **Reporting** module.

## Core rules
- payment, refund, return, and discount reports must remain tenant-scoped
- use clear direction-aware payment interpretation

## Why these rules matter
Finance and store operations need to see money movement and reverse-flow impact clearly.

## Related feature files
- [[10-modules/reporting/features/payment-return-reporting/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]

## Recommended reading order
Read after [[10-modules/reporting/features/payment-return-reporting/overview]], then before [[application]], [[api]], and [[validations]].
