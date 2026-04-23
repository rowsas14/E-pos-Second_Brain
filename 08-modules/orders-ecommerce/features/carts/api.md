<!--
meta:
  title: Orders E-Commerce / Carts / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [orders-ecommerce, carts, api]
-->
> Hub: [[10-modules/orders-ecommerce/features/carts/overview]]

# Carts - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Carts**.

## Endpoints / contract areas
- POST /store/carts
- POST /store/carts/{cartId}/items
- POST /store/carts/{cartId}/merge

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/orders-ecommerce/features/carts/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/catalog/features/variants/overview|Variants]]

## Recommended reading order
Read after [[10-modules/orders-ecommerce/features/carts/overview]], [[business-rules]], [[data-model]], and [[application]].
