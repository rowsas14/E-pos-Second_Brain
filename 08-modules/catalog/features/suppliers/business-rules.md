<!--
meta:
  title: Catalog / Suppliers / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, suppliers, business-rules]
-->

# Suppliers - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Suppliers** feature inside the **Catalog** module.

## Rule set
### BR-001
- Supplier belongs to exactly one tenant.

### BR-002
- At most one primary address may exist per supplier.

### BR-003
- A product-supplier pair must be unique.

### BR-004
- At most one primary supplier may exist per product.

### BR-005
- Supplier mappings and addresses must stay inside the same tenant boundary as the supplier and product.

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
- [[10-modules/catalog/features/brands/overview|Brands]]

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
