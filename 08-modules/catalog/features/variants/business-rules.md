<!--
meta:
  title: Catalog / Variants / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, variants, business-rules]
-->

# Variants - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Variants** feature inside the **Catalog** module.

## Rule set
### BR-001
- SKU must be unique inside one tenant.

### BR-002
- Barcode, if present, must be unique inside one tenant.

### BR-003
- Variant signature, if present, must be unique inside one product.

### BR-004
- Every sellable product must have at least one active variant.

### BR-005
- A variant must belong to the same tenant as its parent product and selected attribute values.

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
- [[10-modules/catalog/features/attributes/overview|Attributes]]
- [[10-modules/catalog/features/product-images/overview|Product Images]]

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
