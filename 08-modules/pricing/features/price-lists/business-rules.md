<!--
meta:
  title: Pricing / Price Lists / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, business-rules]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Price Lists** feature inside the **Pricing** module.

## Core rules
- price list belongs to one tenant
- channel is pos, ecommerce, or both
- list price is required; sale price is optional

## Why these rules matter
Unified commerce needs controlled pricing that can differ by channel and time while still resolving from a shared catalog.

## Related feature files
- [[10-modules/pricing/features/price-lists/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/pricing/features/price-lists/overview]], then before [[application]], [[api]], and [[validations]].
