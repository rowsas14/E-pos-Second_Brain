<!--
meta:
  title: Orders E-Commerce / Product Reviews / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, validations]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Validations

## Purpose
This file records input, business, and **workflow** validations for **Product Reviews**.

## Validation rules
- validate rating range
- ensure product and customer share tenant

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
