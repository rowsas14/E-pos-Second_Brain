<!--
meta:
  title: Catalog / Attributes / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, attributes, business-rules]
-->

# Attributes - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Attributes** feature inside the **Catalog** module.

## Rule set
### BR-001
- Attribute code must be unique inside one tenant.

### BR-002
- Attribute data type must be one of text, number, boolean, or select.

### BR-003
- If an attribute is variant-defining, it must be considered when creating or matching variant combinations.

### BR-004
- Category-attribute mapping must stay inside the same tenant and must not duplicate one attribute on the same category.

### BR-005
- For select-type attributes, chosen attribute_value_id must belong to the same attribute.

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
- [[10-modules/catalog/features/categories/overview|Categories]]
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
