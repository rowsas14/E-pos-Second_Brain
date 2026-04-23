<!--
meta:
  title: Sales POS / Hold & Recall Sales / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, hold-recall-sales, edge-cases]
-->
> Hub: [[10-modules/sales-pos/features/hold-recall-sales/overview]]

# Hold & Recall Sales - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Hold & Recall Sales**.

## Edge cases
- same held sale recalled by two terminals
- held sale stale across session boundary

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/sales-pos/features/hold-recall-sales/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
