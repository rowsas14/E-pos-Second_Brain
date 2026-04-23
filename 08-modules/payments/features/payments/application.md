<!--
meta:
  title: Payments / Payments / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, application]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Payments**.

## Main orchestration paths
- create payment intent/record
- capture inbound payment
- create outbound refund payment

## Application-layer notes
- payment aggregate should not directly own sale/order totals; allocations do that linkage

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
