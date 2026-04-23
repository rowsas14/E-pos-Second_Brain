<!--
meta:
  title: Pricing / Price Lists / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, price-lists, api]
-->
> Hub: [[10-modules/pricing/features/price-lists/overview]]

# Price Lists - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Price Lists**.

## Endpoints / contract areas
- POST /pricing/price-lists
- POST /pricing/price-lists/{priceListId}/items
- PATCH /pricing/price-lists/{priceListId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/pricing/features/price-lists/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/outlet-price-overrides/overview|Outlet Price Overrides]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/pricing/features/price-lists/overview]], [[business-rules]], [[data-model]], and [[application]].
