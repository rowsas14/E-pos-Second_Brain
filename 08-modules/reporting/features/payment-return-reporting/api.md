<!--
meta:
  title: Reporting / Payment & Return Reporting / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [reporting, payment-return-reporting, api]
-->
> Hub: [[10-modules/reporting/features/payment-return-reporting/overview]]

# Payment & Return Reporting - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Payment & Return Reporting**.

## Endpoints / contract areas
- GET /reports/payments
- GET /reports/refunds
- GET /reports/returns
- GET /reports/discounts

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/reporting/features/payment-return-reporting/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/discounts-promotions/features/discount-applications/overview|Discount Applications]]

## Recommended reading order
Read after [[10-modules/reporting/features/payment-return-reporting/overview]], [[business-rules]], [[data-model]], and [[application]].
