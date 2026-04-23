<!--
meta:
  title: Receipts / Receipt Delivery / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, api]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Receipt Delivery**.

## Endpoints / contract areas
- POST /receipts/{receiptId}/print
- POST /receipts/{receiptId}/email
- GET /receipts/{receiptId}/pdf

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/receipts/features/receipt-delivery/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-delivery/overview]], [[business-rules]], [[data-model]], and [[application]].
