<!--
meta:
  title: Reporting / Payment & Return Reporting / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, payment-return-reporting, validations]
-->
> Hub: [[10-modules/reporting/features/payment-return-reporting/overview]]

# Payment & Return Reporting - Validations

## Purpose
This file records input, business, and **workflow** validations for **Payment & Return Reporting**.

## Validation rules
- apply consistent posted/completed/refunded status filters by report definition

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
