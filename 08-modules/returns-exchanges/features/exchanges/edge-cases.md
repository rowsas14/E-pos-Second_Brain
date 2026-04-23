<!--
meta:
  title: Returns & Exchanges / Exchanges / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, exchanges, edge-cases]
-->
> Hub: [[10-modules/returns-exchanges/features/exchanges/overview]]

# Exchanges - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Exchanges**.

## Edge cases
- new items cheaper than returned items
- mixed collect and refund not allowed in one exchange under current model

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/returns-exchanges/features/exchanges/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
