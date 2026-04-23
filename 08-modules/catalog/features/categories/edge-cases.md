<!--
meta:
  title: Catalog / Categories / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, edge-cases]
-->

# Categories - Edge Cases

Back to [[overview]]

## Purpose
This file captures uncommon, failure-prone, or migration-sensitive scenarios for **Categories**.

## Edge cases
- moving a category with children
- archiving a category still linked to active products
- merging duplicate categories during onboarding cleanup

## Operational caution
- catalog changes can have delayed impact on POS search, storefront display, pricing, and stock workflows
- historical documents should remain explainable even after catalog master data changes
- onboarding and dedupe flows need extra review when incoming source quality is weak

## Related files
- [[business-rules]]
- [[validations]]
- [[bugs]]
- [[changelog]]
