<!--
meta:
  title: Receipts / Receipt Generation / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, api]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Receipt Generation**.

## Endpoints / contract areas
- POST /receipts/generate
- GET /receipts/{receiptId}
- GET /documents/{documentId}/receipts

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/receipts/features/receipt-generation/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-generation/overview]], [[business-rules]], [[data-model]], and [[application]].
