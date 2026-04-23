<!--
meta:
  title: Catalog / Attributes / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, attributes, overview]
-->

# Attributes

## Purpose
Tenant-owned attribute system used to define product characteristics such as size, color, storage, or volume and to support variant construction through selected values.

## Why this feature exists
This feature exists because the unified commerce model needs one tenant-owned catalog foundation that can serve both POS and E-Commerce without duplicating master data. The main persistence anchors are `product_attributes`, `attribute_values`, `category_attributes`, `variant_attribute_values`. The feature must remain tenant-safe and reusable across admin setup, operational search, pricing, inventory, sales, and orders.

## Scope
In scope:
- define tenant-owned attributes
- maintain selectable values
- mark whether an attribute is variant-defining
- map attributes to categories
- store chosen values per variant

Out of scope:
- global platform-wide attribute master
- arbitrary formula engine on attribute values
- customer-facing configurable product builder at runtime

## Key project context
- module: `catalog`
- channels supported: `both`
- tenant ownership: tenant-owned
- primary related tables: `product_attributes`, `attribute_values`, `category_attributes`, `variant_attribute_values`
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
- [[10-modules/catalog/features/categories/overview|Categories]]
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/catalog/features/variants/overview|Variants]]

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
- schema rules change for `product_attributes`, `attribute_values`, `category_attributes`, `variant_attribute_values`
- tenant ownership changes
- POS or E-Commerce usage changes
- API contract changes
- validations or permissions change
- a new recurring defect or behavior change appears

## Notes
- Attributes are configuration-level catalog structure.
- Variant creation and duplicate prevention depend on consistent attribute usage.
