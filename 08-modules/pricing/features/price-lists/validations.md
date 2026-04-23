<!--
meta:
  title: Pricing / Price Lists / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, validations]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - Validations

## Purpose
This file records input, business, and **workflow** validations for **Price Lists**.

## Validation rules
- ensure variant belongs to same tenant as price list
- validate active date range and currency
- prevent duplicate price item keys under same scope

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
