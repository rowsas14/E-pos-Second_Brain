<!--
meta:
  title: Receipts / Receipt Delivery / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, edge-cases]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Receipt Delivery**.

## Edge cases
- printer offline
- email send fails after sale is completed

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/receipts/features/receipt-delivery/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
