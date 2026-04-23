<!--
meta:
  title: Sales POS / Tills & Sessions / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, backend]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Backend

## Purpose
This file captures **backend** implementation details for the .NET **Clean Architecture** solution.

## Backend implementation notes
- session open/close should be explicit use cases with reconciliation checks

## Expected code areas
- **Domain** model or domain service where core rule belongs
- **Application** service/use case orchestration
- **Infrastructure** persistence and external **integration**
- **Repository**, **validation**, and transaction boundaries aligned to the feature

## Related feature files
- [[10-modules/sales-pos/features/tills-sessions/overview]]
- [[application]]
- [[data-model]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[application]], [[data-model]], and [[validations]].
