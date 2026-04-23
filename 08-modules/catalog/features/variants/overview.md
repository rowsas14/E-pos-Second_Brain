<!--
meta:
  title: Catalog / Variants / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, variants, overview]
-->

# Variants

## Purpose
Sellable sku/barcode units under a product that carry the operational identity used by pricing, inventory, cart, sale, order, return, and exchange flows.

## Why this feature exists
This feature exists because the unified commerce model needs one tenant-owned catalog foundation that can serve both POS and E-Commerce without duplicating master data. The main persistence anchors are `product_variants`, `variant_attribute_values`. The feature must remain tenant-safe and reusable across admin setup, operational search, pricing, inventory, sales, and orders.

## Scope
In scope:
- create and maintain sellable variants
- assign SKU and optional barcode
- track variant status
- store purchase limits and selected attribute values
- support canonical variant signature

Out of scope:
- inventory balances or pricing themselves
- customer-configured runtime product generation
- cross-product shared variant identities

## Key project context
- module: `catalog`
- channels supported: `both`
- tenant ownership: tenant-owned
- primary related tables: `product_variants`, `variant_attribute_values`
- operational dependency: this feature supports shared catalog foundations used by POS and E-Commerce

## Navigation hub
- [[business-rules]]
- [[data-model]]
- [[application]]
- [[api]]
- [[workflows]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]
- [[bugs]]
- [[changelog]]
- [[backend]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/catalog/features/attributes/overview|Attributes]]
- [[10-modules/catalog/features/product-images/overview|Product Images]]

## Related cross-folder docs
- [[01-product/product-overview]]
- [[02-domain/domain-overview]]
- [[02-domain/tenancy-model]]
- [[04-architecture/unified-commerce-architecture]]
- [[06-database/database-overview]]
- [[06-database/entity-relationship-overview]]
- [[07-api/api-standards]]
- [[08-backend/backend-overview]]

## Work this feature supports
- feature implementation and review
- business-rule clarification before coding
- schema and API alignment for catalog changes
- admin and storefront behavior clarification
- controlled bug fixing and change tracking

## Recommended reading order
1. [[overview]]
2. [[business-rules]]
3. [[data-model]]
4. [[application]]
5. [[api]]
6. [[permissions]]
7. [[validations]]
8. [[workflows]]
9. [[edge-cases]]
10. [[backend]]
11. [[frontend]]
12. [[bugs]]
13. [[changelog]]

## Update triggers
- schema rules change for `product_variants`, `variant_attribute_values`
- tenant ownership changes
- POS or E-Commerce usage changes
- API contract changes
- validations or permissions change
- a new recurring defect or behavior change appears

## Notes
- Variant is the sellable transaction unit for this project.
- Do not design operational flows around productId alone where actual sale/order behavior needs variantId.
