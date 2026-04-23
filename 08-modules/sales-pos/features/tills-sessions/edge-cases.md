<!--
meta:
  title: Sales POS / Tills & Sessions / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, edge-cases]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Tills & Sessions**.

## Edge cases
- browser crash with session still open
- till moved to maintenance while session exists

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/sales-pos/features/tills-sessions/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
