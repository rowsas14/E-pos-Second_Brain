<!--
meta:
  title: Catalog / Attributes / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, attributes, data-model]
-->

# Attributes - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Attributes**.

## Primary tables
- `product_attributes`
- `attribute_values`
- `category_attributes`
- `variant_attribute_values`

## Main structure
- `product_attributes`: tenant-owned definitions, `code`, `name`, `data_type`, `is_variant_defining`, `status`
- `attribute_values`: allowed values for selectable attributes
- `category_attributes`: category-to-attribute mapping
- `variant_attribute_values`: selected values per variant

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- `UNIQUE (tenant_id, code)` for attributes
- `UNIQUE (attribute_id, value_code)` for selectable values
- `UNIQUE (variant_id, attribute_id)` for selected values
- attribute value must belong to the same attribute

## Main relationships
- related to [[10-modules/catalog/features/categories/overview|Categories]]
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
