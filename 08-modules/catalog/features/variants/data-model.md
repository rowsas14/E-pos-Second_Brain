<!--
meta:
  title: Catalog / Variants / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, variants, data-model]
-->

# Variants - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Variants**.

## Primary tables
- `product_variants`
- `variant_attribute_values`

## Main structure
- `product_variants`: `tenant_id`, `product_id`, `sku`, optional `barcode`, `name`, `variant_signature`, limits, `status`
- `variant_attribute_values`: selected attribute values attached to one variant

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- `UNIQUE (tenant_id, sku)`
- `UNIQUE (tenant_id, barcode)` where barcode is not null
- `UNIQUE (product_id, variant_signature)` where signature is not null

## Main relationships
- related to [[10-modules/catalog/features/products/overview|Products]]
- related to [[10-modules/catalog/features/attributes/overview|Attributes]]
- related to [[10-modules/catalog/features/product-images/overview|Product Images]]
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
