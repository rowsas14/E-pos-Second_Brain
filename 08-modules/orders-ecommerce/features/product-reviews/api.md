<!--
meta:
  title: Orders E-Commerce / Product Reviews / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, product-reviews, api]
-->
> Hub: [[10-modules/orders-ecommerce/features/product-reviews/overview]]

# Product Reviews - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Product Reviews**.

## Endpoints / contract areas
- POST /store/products/{productId}/reviews
- GET /store/products/{productId}/reviews
- PATCH /reviews/{reviewId}/status

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/orders-ecommerce/features/product-reviews/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/product-reviews/overview]], [[business-rules]], [[data-model]], and [[application]].
