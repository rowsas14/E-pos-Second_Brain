<!--
meta:
  title: Catalog / Products / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, products, data-model]
-->

# Products - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Products**.

## Primary tables
- `products`
- `tax_classes`
- `return_policy_types`

## Main structure
- `products`: `tenant_id`, `category_id`, `brand_id`, `tax_class_id`, `product_type`, descriptions, channel sellability flags, `return_policy_type_id`, `status`
- references tenant-owned `tax_classes` and shared reference `return_policy_types`

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- `UNIQUE (tenant_id, slug)`
- product type is `simple | variant_parent | bundle | service`
- status is `draft | active | archived`
- sellable products require active variants

## Main relationships
- related to [[10-modules/catalog/features/brands/overview|Brands]]
- related to [[10-modules/catalog/features/categories/overview|Categories]]
- related to [[10-modules/catalog/features/variants/overview|Variants]]
- related to [[10-modules/catalog/features/product-images/overview|Product Images]]
- related to [[10-modules/catalog/features/suppliers/overview|Suppliers]]
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
