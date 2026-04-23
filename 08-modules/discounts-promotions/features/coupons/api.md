<!--
meta:
  title: Discounts & Promotions / Coupons / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, coupons, api]
-->
> Hub: [[10-modules/discounts-promotions/features/coupons/overview]]

# Coupons - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Coupons**.

## Endpoints / contract areas
- POST /coupons
- POST /coupons/{code}/validate
- POST /coupons/{code}/redeem

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/discounts-promotions/features/coupons/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/coupons/overview]], [[business-rules]], [[data-model]], and [[application]].
