<!--
meta:
  title: Catalog / Product Images / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, product-images, edge-cases]
-->

# Product Images - Edge Cases

Back to [[overview]]

## Purpose
This file captures uncommon, failure-prone, or migration-sensitive scenarios for **Product Images**.

## Edge cases
- primary image removal
- variant-specific image with wrong parent product
- storefront showing no image for active online product

## Operational caution
- catalog changes can have delayed impact on POS search, storefront display, pricing, and stock workflows
- historical documents should remain explainable even after catalog master data changes
- onboarding and dedupe flows need extra review when incoming source quality is weak

## Related files
- [[business-rules]]
- [[validations]]
- [[bugs]]
- [[changelog]]
