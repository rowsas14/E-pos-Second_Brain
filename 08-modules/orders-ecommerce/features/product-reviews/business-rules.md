<!--
meta:
  title: Orders E-Commerce / Product Reviews / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, business-rules]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Product Reviews** feature inside the **Orders E-Commerce** module.

## Core rules
- review belongs to tenant, customer, and product
- rating range is 1 to 5
- review status moves through pending, approved, or rejected

## Why these rules matter
Reviews are part of E-Commerce experience and require moderated tenant-owned content.

## Related feature files
- [[10-modules/orders-ecommerce/features/product-reviews/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/product-reviews/overview]], then before [[application]], [[api]], and [[validations]].
