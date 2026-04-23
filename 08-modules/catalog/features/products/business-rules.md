<!--
meta:
  title: Catalog / Products / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, products, business-rules]
-->

# Products - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Products** feature inside the **Catalog** module.

## Rule set
### BR-001
- Product slug must be unique inside one tenant.

### BR-002
- Product type must be one of simple, variant_parent, bundle, or service.

### BR-003
- Status must be one of draft, active, or archived.

### BR-004
- A sellable product must have at least one active variant before operational use.

### BR-005
- Category, brand, tax class, and return policy references must stay within the same tenant boundary where tenant-owned.

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
- [[10-modules/catalog/features/brands/overview|Brands]]
- [[10-modules/catalog/features/categories/overview|Categories]]
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/catalog/features/product-images/overview|Product Images]]
- [[10-modules/catalog/features/suppliers/overview|Suppliers]]

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
