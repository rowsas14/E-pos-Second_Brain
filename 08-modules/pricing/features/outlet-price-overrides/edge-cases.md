<!--
meta:
  title: Pricing / Outlet Price Overrides / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, outlet-price-overrides, edge-cases]
-->
> Hub: [[10-modules/pricing/features/outlet-price-overrides/overview]]

# Outlet Price Overrides - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Outlet Price Overrides**.

## Edge cases
- POS terminal switched to another outlet but cached old price
- E-Commerce incorrectly using outlet override

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/pricing/features/outlet-price-overrides/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
