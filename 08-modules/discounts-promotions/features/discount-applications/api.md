<!--
meta:
  title: Discounts & Promotions / Discount Applications / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [discounts-promotions, discount-applications, api]
-->
> Hub: [[10-modules/discounts-promotions/features/discount-applications/overview]]

# Discount Applications - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Discount Applications**.

## Endpoints / contract areas
- POST /discounts/applications
- DELETE /discounts/applications/{applicationId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/discounts-promotions/features/discount-applications/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/discounts-promotions/features/discount-requests/overview|Discount Requests]]
- [[10-modules/discounts-promotions/features/coupons/overview|Coupons]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]

## Recommended reading order
Read after [[10-modules/discounts-promotions/features/discount-applications/overview]], [[business-rules]], [[data-model]], and [[application]].
