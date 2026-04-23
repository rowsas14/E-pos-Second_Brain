<!--
meta:
  title: Payments / Payment Allocations / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payment-allocations, api]
-->
> Hub: [[10-modules/payments/features/payment-allocations/overview]]

# Payment Allocations - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Payment Allocations**.

## Endpoints / contract areas
- POST /payments/{paymentId}/allocate/sale
- POST /payments/{paymentId}/allocate/order

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/payments/features/payment-allocations/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]
- [[10-modules/payments/features/payments/overview|Payments]]

## Recommended reading order
Read after [[10-modules/payments/features/payment-allocations/overview]], [[business-rules]], [[data-model]], and [[application]].
