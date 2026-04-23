<!--
meta:
  title: Tax / Tax Classes / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, data-model]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Data Model

## Purpose
This file shows the main **entity**, table, and relationship impact for **Tax Classes**.

## Primary entities
- tax_classes
- products

## Data impact
- This feature stores and reads data under strict **tenant** boundaries.
- Downstream **workflow**, **API**, and reporting behavior depends on the entities above.
- Changes here usually affect **validation**, **repository**, and transaction handling.

## Related feature files
- [[10-modules/tax/features/tax-classes/overview]]
- [[business-rules]]
- [[application]]
- [[api]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-classes/overview]] and [[business-rules]], then before [[application]] and [[api]].
