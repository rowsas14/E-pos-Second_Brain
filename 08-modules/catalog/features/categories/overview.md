<!--
meta:
  title: Catalog / Categories / Overview
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, overview]
-->

# Categories

## Purpose
Tenant-owned hierarchical category structure used to organize products, drive discovery, and control which attributes are relevant during catalog maintenance.

## Why this feature exists
This feature exists because the unified commerce model needs one tenant-owned catalog foundation that can serve both POS and E-Commerce without duplicating master data. The main persistence anchors are `categories`, `category_attributes`. The feature must remain tenant-safe and reusable across admin setup, operational search, pricing, inventory, sales, and orders.

## Scope
In scope:
- maintain category tree per tenant
- assign parent/child hierarchy
- map categories to allowed attributes
- support storefront and back-office navigation

Out of scope:
- cross-tenant shared category tree
- dynamic rules engine for category inheritance beyond current schema
- SEO page-builder behavior

## Key project context
- module: `catalog`
- channels supported: `both`
- tenant ownership: tenant-owned
- primary related tables: `categories`, `category_attributes`
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
- schema rules change for `categories`, `category_attributes`
- tenant ownership changes
- POS or E-Commerce usage changes
- API contract changes
- validations or permissions change
- a new recurring defect or behavior change appears

## Notes
- Category is mainly an organization and setup aid.
- Category influences product discovery and relevant attribute exposure, but sellable transaction behavior still happens at variant level.
