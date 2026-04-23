<!--
meta:
  title: Catalog / Product Images / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, product-images, data-model]
-->

# Product Images - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Product Images**.

## Primary tables
- `product_images`

## Main structure
- `product_images`: `tenant_id`, `product_id`, optional `variant_id`, `storage_key`, `alt_text`, `sort_order`, `is_primary`

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- at most one primary product-level image
- at most one primary variant-level image for a given variant
- variant image must still belong to the same product and tenant

## Main relationships
- related to [[10-modules/catalog/features/products/overview|Products]]
- related to [[10-modules/catalog/features/variants/overview|Variants]]
- linked to downstream pricing, inventory, sales, orders, returns, and reporting through catalog identity

## Data impact notes
- changes here can affect search, sellability, barcode lookup, pricing resolution, and stock flows
- historical transactions should rely on frozen snapshots where required rather than live catalog mutation

## Related files
- [[business-rules]]
- [[application]]
- [[validations]]
- [[06-database/database-overview]]
- [[06-database/tenant-scoping-rules]]
