<!--
meta:
  title: Catalog / Brands / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, brands, business-rules]
-->

# Brands - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Brands** feature inside the **Catalog** module.

## Rule set
### BR-001
- Brand name must be unique inside one tenant.

### BR-002
- Brand code is optional, but if used it must be unique inside the tenant.

### BR-003
- A product may exist without a brand, but if a brand is assigned it must belong to the same tenant as the product.

### BR-004
- Inactive brands must not be offered for new product assignments, but historical product references remain valid.

### BR-005
- Brand changes must not rewrite historical sale, order, or receipt snapshots.

## Additional guardrails
- This feature is tenant-owned and must never cross tenant boundaries.
- POS and E-Commerce can consume the same catalog foundation, but operational behavior must still respect channel-specific rules.
- Historical transactions must not be invalidated by later catalog maintenance.

## Why these rules matter
Catalog data is reused by pricing, stock, sales, orders, returns, exchanges, search, and reporting. Weak rules here create duplicate data, wrong sellability, broken barcode lookup, and inconsistent downstream behavior.

## Related files
- [[overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[workflows]]
- [[api]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/catalog/features/categories/overview|Categories]]

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
