<!--
meta:
  title: Catalog / Product Images / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, product-images, business-rules]
-->

# Product Images - Business Rules

Back to [[overview]]

## Purpose
This file captures the business restrictions and ownership rules for the **Product Images** feature inside the **Catalog** module.

## Rule set
### BR-001
- Each image belongs to one tenant and one product.

### BR-002
- An image may optionally point to one variant for variant-specific display.

### BR-003
- At most one primary product-level image and one primary variant-level image may exist for the related object.

### BR-004
- Deleting or replacing an image must not break historical transactions because sales and orders use frozen text/pricing snapshots, not live image data.

### BR-005
- Storefront use must respect product and variant publishing state.

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
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[overview]], then before [[application]], [[api]], and [[validations]].
