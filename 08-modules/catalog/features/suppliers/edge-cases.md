<!--
meta:
  title: Catalog / Suppliers / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, suppliers, edge-cases]
-->

# Suppliers - Edge Cases

Back to [[overview]]

## Purpose
This file captures uncommon, failure-prone, or migration-sensitive scenarios for **Suppliers**.

## Edge cases
- multiple import rows creating duplicate suppliers
- changing primary supplier when historical mappings exist
- blocked supplier still referenced by active products

## Operational caution
- catalog changes can have delayed impact on POS search, storefront display, pricing, and stock workflows
- historical documents should remain explainable even after catalog master data changes
- onboarding and dedupe flows need extra review when incoming source quality is weak

## Related files
- [[business-rules]]
- [[validations]]
- [[bugs]]
- [[changelog]]
