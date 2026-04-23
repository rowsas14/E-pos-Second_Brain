<!--
meta:
  title: Payments / Refunds / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, backend]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- refund service should coordinate original payment, outbound payment, and return/exchange allocation

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/payments/features/refunds/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
