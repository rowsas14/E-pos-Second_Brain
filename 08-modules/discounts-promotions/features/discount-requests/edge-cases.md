<!--
meta:
  title: Discounts & Promotions / Discount Requests / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, edge-cases]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Discount Requests**.

## Edge cases
- request expires while cashier waits at counter
- request approved after sale already completed or voided

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-requests/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
