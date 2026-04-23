<!--
meta:
  title: Pricing / Outlet Price Overrides / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, outlet-price-overrides, business-rules]
-->
> Hub: [[10-modules/pricing/features/outlet-price-overrides/overview]]

# Outlet Price Overrides - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Outlet Price Overrides** feature inside the **Pricing** module.

## Core rules
- outlet override is stored at price list item level
- override must still belong to same tenant and valid outlet
- resolution order must be deterministic: outlet override before generic item when applicable

## Why these rules matter
Stores may need outlet-specific price differences while still using the same tenant catalog and price list infrastructure.

## Related feature files
- [[10-modules/pricing/features/outlet-price-overrides/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/pricing/features/outlet-price-overrides/overview]], then before [[application]], [[api]], and [[validations]].
