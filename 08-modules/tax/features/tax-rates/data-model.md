<!--
meta:
  title: Tax / Tax Rates / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, data-model]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Tax Rates**.

## Primary entities
- tax_rates

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/tax/features/tax-rates/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-rates/overview]] and [[business-rules]], then before [[application]] and [[api]].
