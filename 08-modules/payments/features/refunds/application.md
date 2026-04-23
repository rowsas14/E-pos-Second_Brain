<!--
meta:
  title: Payments / Refunds / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, application]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Refunds**.

## Main orchestration paths
- create refund request/result from return or cancellation
- issue outbound payment
- allocate refund to return or exchange document

## Application-layer notes
- refund service should coordinate original payment, outbound payment, and return/exchange allocation

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
