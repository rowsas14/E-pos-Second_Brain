<!--
meta:
  title: Catalog / Categories / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, business-rules]
-->

# Categories - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Categories** feature inside the **Catalog** module.

## Rule set
### BR-001
- Category slug must be unique inside one tenant.

### BR-002
- If a parent category is used, parent and child must belong to the same tenant.

### BR-003
- Category hierarchy must not create circular parent references.

### BR-004
- Category-attribute mapping must remain same-tenant and should reflect only attributes relevant for setup.

### BR-005
- Deactivating a category must not destroy historical product or order references.

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

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
