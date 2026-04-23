<!--
meta:
  title: Catalog / Products / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, products, overview]
-->

# Products

## Purpose
Tenant-owned product master shared across pos and e-commerce, holding commercial identity, channel sellability, tax class, return policy, descriptions, and parent context for variants.

## Why this feature exists
This feature exists because the unified commerce model needs one tenant-owned catalog foundation that can serve both POS and E-Commerce without duplicating master data. The main persistence anchors are `products`, `tax_classes`, `return_policy_types`. The feature must remain tenant-safe and reusable across admin setup, operational search, pricing, inventory, sales, and orders.

## Scope
In scope:
- create and maintain product master
- manage channel sellability flags
- assign category, brand, tax class, and return policy
- control draft/active/archived status

Out of scope:
- sellable stock-keeping behavior without variants
- procurement transactions
- campaign-specific pricing

## Key project context
- module: `catalog`
- channels supported: `both`
- tenant ownership: tenant-owned
- primary related tables: `products`, `tax_classes`, `return_policy_types`
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
- [[10-modules/catalog/features/brands/overview|Brands]]
- [[10-modules/catalog/features/categories/overview|Categories]]
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/catalog/features/product-images/overview|Product Images]]
- [[10-modules/catalog/features/suppliers/overview|Suppliers]]

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
- schema rules change for `products`, `tax_classes`, `return_policy_types`
- tenant ownership changes
- POS or E-Commerce usage changes
- API contract changes
- validations or permissions change
- a new recurring defect or behavior change appears

## Notes
- Product is the business-facing item definition.
- Price, stock, cart, sale, and order flows still operate on variant_id rather than product_id alone.
