<!--
meta:
  title: Reporting / Payment & Return Reporting / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, payment-return-reporting, application]
-->
> Hub: [[10-modules/reporting/features/payment-return-reporting/overview]]

# Payment & Return Reporting - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Payment & Return Reporting**.

## Main orchestration paths
- review payment method mix
- review refund volume
- review return and discount exposure

## Application-layer notes
- consider denormalized read models if real-time dashboard queries become heavy

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
