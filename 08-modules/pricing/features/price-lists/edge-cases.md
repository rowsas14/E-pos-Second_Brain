<!--
meta:
  title: Pricing / Price Lists / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, edge-cases]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Price Lists**.

## Edge cases
- multiple active price lists with overlapping periods
- e-commerce promotional pricing while POS uses base price

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/pricing/features/price-lists/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
