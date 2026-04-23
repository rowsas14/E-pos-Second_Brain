<!--
meta:
  title: Catalog / Products / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, products, edge-cases]
-->

# Products - Edge Cases

Back to [[overview]]

## Purpose
This file captures uncommon, failure-prone, or migration-sensitive scenarios for **Products**.

## Edge cases
- archiving product with active variants
- changing product type after variants and transactions exist
- product marked sellable online without images or pricing readiness

## Operational caution
- catalog changes can have delayed impact on POS search, storefront display, pricing, and stock workflows
- historical documents should remain explainable even after catalog master data changes
- onboarding and dedupe flows need extra review when incoming source quality is weak

## Related files
- [[business-rules]]
- [[validations]]
- [[bugs]]
- [[changelog]]
