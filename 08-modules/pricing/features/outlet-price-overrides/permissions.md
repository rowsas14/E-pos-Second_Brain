<!--
meta:
  title: Pricing / Outlet Price Overrides / Permissions
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, outlet-price-overrides, permissions]
-->
> Hub: [[10-modules/pricing/features/outlet-price-overrides/overview]]

# Outlet Price Overrides - Permissions

## Purpose
This file explains role and permission behavior for **Outlet Price Overrides**.

## Permission behavior
- pricing admin or authorized tenant admin manages overrides

## Why permission rules matter
- This project has strict **tenant** isolation.
- Sensitive actions such as discounts, refunds, stock adjustment, and administration should never rely only on hidden buttons.
- **API**, **frontend**, and **workflow** behavior must resolve the same permission logic.

## Related feature files
- [[10-modules/pricing/features/outlet-price-overrides/overview]]
- [[business-rules]]
- [[api]]
- [[frontend]]

## Related features
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/pricing/features/outlet-price-overrides/overview]] and before exposing [[api]] or [[frontend]] changes.
