<!--
meta:
  title: Payments / Provider Transactions / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, application]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Provider Transactions**.

## Main orchestration paths
- store auth/capture response
- store webhook callback
- store failure/refund event

## Application-layer notes
- webhook handler must be idempotent and decouple parsing from payment state transition policy

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
