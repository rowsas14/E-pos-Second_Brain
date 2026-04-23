<!--
meta:
  title: Pricing / Outlet Price Overrides / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, outlet-price-overrides, validations]
-->
> Hub: [[10-modules/pricing/features/outlet-price-overrides/overview]]

# Outlet Price Overrides - Validations

## Purpose
This file records input, business, and **workflow** validations for **Outlet Price Overrides**.

## Validation rules
- ensure outlet, variant, and price list share tenant
- avoid duplicate outlet override row for same list and variant

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
