<!--
meta:
  title: Pricing / Price Lists / Application
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, application]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - Application

## Purpose
This file documents **use-case orchestration**, **service** responsibilities, and transactional behavior for **Price Lists**.

## Main orchestration paths
- create price list
- add variant prices
- activate price list for effective period

## Application-layer notes
- pricing resolution service should be reusable by cart, sale, and order modules
- keep snapshot generation in transaction modules, not pricing master endpoints

## Dependent files
- [[business-rules]]
- [[data-model]]
- [[api]]
- [[validations]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
