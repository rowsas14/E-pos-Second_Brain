<!--
meta:
  title: Receipts / Receipt Generation / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, edge-cases]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Receipt Generation**.

## Edge cases
- thermal print succeeds but DB receipt record fails
- reprint after document updated; original snapshot must remain stable

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/receipts/features/receipt-generation/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
