<!--
meta:
  title: Pricing / Outlet Price Overrides / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, outlet-price-overrides, application]
-->
> Hub: [[10-modules/pricing/features/outlet-price-overrides/overview]]

# Outlet Price Overrides - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Outlet Price Overrides**.

## Main orchestration paths
- set outlet-specific price for a variant
- review override impact before activation

## Application-layer notes
- pricing resolver must receive outlet context explicitly for POS flows

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
