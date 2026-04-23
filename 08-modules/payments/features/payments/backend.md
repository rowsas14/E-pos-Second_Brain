<!--
meta:
  title: Payments / Payments / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, backend]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- payment aggregate should not directly own sale/order totals; allocations do that linkage

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/payments/features/payments/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
