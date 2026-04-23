<!--
meta:
  title: Discounts & Promotions / Discount Requests / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-requests, api]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-requests/overview]]

# Discount Requests - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Discount Requests**.

## Endpoints / contract areas
- POST /discounts/requests
- PATCH /discounts/requests/{requestId}/approve
- PATCH /discounts/requests/{requestId}/reject

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-requests/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-requests/overview]], [[business-rules]], [[data-model]], and [[application]].
