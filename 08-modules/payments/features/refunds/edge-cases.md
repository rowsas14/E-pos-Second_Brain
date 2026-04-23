<!--
meta:
  title: Payments / Refunds / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, refunds, edge-cases]
-->
> Hub: [[10-modules/payments/features/refunds/overview]]

# Refunds - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Refunds**.

## Edge cases
- manual cash refund without gateway row
- multiple partial refunds against one original payment

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/payments/features/refunds/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
