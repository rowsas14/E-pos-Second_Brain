<!--
meta:
  title: Catalog / Attributes / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, attributes, edge-cases]
-->

# Attributes - Edge Cases

Back to [[overview]]

## Purpose
This file captures uncommon, failure-prone, or migration-sensitive scenarios for **Attributes**.

## Edge cases
- changing is_variant_defining after variants already exist
- switching attribute data_type after values are in use
- retiring attribute values used by active variants

## Operational caution
- catalog changes can have delayed impact on POS search, storefront display, pricing, and stock workflows
- historical documents should remain explainable even after catalog master data changes
- onboarding and dedupe flows need extra review when incoming source quality is weak

## Related files
- [[business-rules]]
- [[validations]]
- [[bugs]]
- [[changelog]]
