<!--
meta:
  title: Catalog / Categories / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, data-model]
-->

# Categories - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Categories**.

## Primary tables
- `categories`
- `category_attributes`

## Main structure
- `categories`: `tenant_id`, optional `parent_id`, `name`, `slug`, `sort_order`, `is_active`
- `category_attributes`: maps one category to relevant attributes with required flag and order

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- `UNIQUE (tenant_id, slug)`
- parent category must belong to same tenant
- `UNIQUE (category_id, attribute_id)` on mappings

## Main relationships
- related to [[10-modules/catalog/features/products/overview|Products]]
- related to [[10-modules/catalog/features/attributes/overview|Attributes]]
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
