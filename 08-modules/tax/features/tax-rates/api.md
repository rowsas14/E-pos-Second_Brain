<!--
meta:
  title: Tax / Tax Rates / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, api]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Tax Rates**.

## Endpoints / contract areas
- POST /tax/rates
- GET /tax/rates
- PATCH /tax/rates/{taxRateId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/tax/features/tax-rates/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-rates/overview]], [[business-rules]], [[data-model]], and [[application]].
