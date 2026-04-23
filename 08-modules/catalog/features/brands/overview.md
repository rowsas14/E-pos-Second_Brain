<!--
meta:
  title: Catalog / Brands / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, brands, overview]
-->

# Brands

## Purpose
Optional tenant-owned brand master used to group products, improve search/filtering, support onboarding dedupe, and keep product presentation consistent across pos and e-commerce.

## Why this feature exists
This feature exists because the unified commerce model needs one tenant-owned catalog foundation that can serve both POS and E-Commerce without duplicating master data. The main persistence anchors are `brands`. The feature must remain tenant-safe and reusable across admin setup, operational search, pricing, inventory, sales, and orders.

## Scope
In scope:
- maintain tenant-owned brand records
- assign brands to products
- support brand-based search, filtering, and merchandising

Out of scope:
- global shared brand catalog across all tenants
- brand-level procurement workflow
- marketing campaign management

## Key project context
- module: `catalog`
- channels supported: `both`
- tenant ownership: tenant-owned
- primary related tables: `brands`
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
- [[10-modules/catalog/features/categories/overview|Categories]]

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
- schema rules change for `brands`
- tenant ownership changes
- POS or E-Commerce usage changes
- API contract changes
- validations or permissions change
- a new recurring defect or behavior change appears

## Notes
- Brand is a merchandising and identification aid, not the sellable transaction unit.
- Keep brand management simple so onboarding and product maintenance stay fast.
