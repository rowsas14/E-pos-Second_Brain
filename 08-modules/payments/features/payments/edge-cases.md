<!--
meta:
  title: Payments / Payments / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, edge-cases]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Payments**.

## Edge cases
- cash captured in POS while card payment still pending
- outbound refund initiated without original payment reference

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/payments/features/payments/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
