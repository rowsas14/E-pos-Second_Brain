<!--
meta:
  title: Catalog / Brands / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, brands, data-model]
-->

# Brands - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Brands**.

## Primary tables
- `brands`

## Main structure
- `brands`: `tenant_id`, `name`, optional `code`, `status`
- linked from `products.brand_id`

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- `UNIQUE (tenant_id, name)`
- `UNIQUE (tenant_id, code)` where code is not null

## Main relationships
- related to [[10-modules/catalog/features/products/overview|Products]]
- related to [[10-modules/catalog/features/categories/overview|Categories]]
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
