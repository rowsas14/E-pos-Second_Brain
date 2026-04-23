<!--
meta:
  title: Returns & Exchanges / Exchanges / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, exchanges, application]
-->
> Hub: [[10-modules/returns-exchanges/features/exchanges/overview]]

# Exchanges - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Exchanges**.

## Main orchestration paths
- create exchange from approved return
- select new items
- collect difference or issue refund

## Application-layer notes
- exchange service should reuse pricing and payment modules while preserving explicit exchange state

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
