<!--
meta:
  title: Returns & Exchanges / Returns / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [returns-exchanges, returns, edge-cases]
-->
> Hub: [[10-modules/returns-exchanges/features/returns/overview]]

# Returns - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Returns**.

## Edge cases
- return against partially fulfilled order
- original outlet differs from processing outlet

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/returns-exchanges/features/returns/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
