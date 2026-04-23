<!--
meta:
  title: Payments / Provider Transactions / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, provider-transactions, backend]
-->
> Hub: [[10-modules/payments/features/provider-transactions/overview]]

# Provider Transactions - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- webhook handler must be idempotent and decouple parsing from payment state transition policy

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/payments/features/provider-transactions/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/payments/features/payments/overview|Payments]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
