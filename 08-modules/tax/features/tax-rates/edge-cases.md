<!--
meta:
  title: Tax / Tax Rates / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, edge-cases]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Tax Rates**.

## Edge cases
- rate changes mid-day while sales/orders already in progress

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/tax/features/tax-rates/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
