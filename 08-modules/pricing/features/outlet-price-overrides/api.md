<!--
meta:
  title: Pricing / Outlet Price Overrides / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [pricing, outlet-price-overrides, api]
-->
> Hub: [[10-modules/pricing/features/outlet-price-overrides/overview]]

# Outlet Price Overrides - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Outlet Price Overrides**.

## Endpoints / contract areas
- POST /pricing/price-lists/{priceListId}/items/{variantId}/outlet-overrides
- DELETE /pricing/price-lists/{priceListId}/items/{variantId}/outlet-overrides/{outletId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/pricing/features/outlet-price-overrides/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[10-modules/pricing/features/outlet-price-overrides/overview]], [[business-rules]], [[data-model]], and [[application]].
