<!--
meta:
  title: Catalog / Suppliers / Data Model
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, suppliers, data-model]
-->

# Suppliers - Data Model

Back to [[overview]]

## Purpose
This file explains the schema impact and main entity relationships for **Suppliers**.

## Primary tables
- `suppliers`
- `supplier_addresses`
- `product_suppliers`

## Main structure
- `suppliers`: tenant-owned supplier header
- `supplier_addresses`: addresses under supplier with one optional primary
- `product_suppliers`: product-to-supplier mapping with supplier SKU, purchase price, lead time, and primary flag

## Tenant ownership
- all operational rows in this feature are tenant-owned or tenant-scoped through parent records
- cross-tenant assignment is never allowed
- related records used by this feature must stay inside the same tenant boundary

## Key constraints
- one supplier-product pair per mapping
- at most one primary supplier per product
- at most one primary address per supplier

## Main relationships
- related to [[10-modules/catalog/features/products/overview|Products]]
- related to [[10-modules/catalog/features/brands/overview|Brands]]
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
