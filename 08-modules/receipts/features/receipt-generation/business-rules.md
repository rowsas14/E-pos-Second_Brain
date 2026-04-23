<!--
meta:
  title: Receipts / Receipt Generation / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, business-rules]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Receipt Generation** feature inside the **Receipts** module.

## Core rules
- receipt stores document_type, document_id, format_type, and payload snapshot
- receipt number unique within tenant

## Why these rules matter
Operational documents need frozen render payloads for reprint, PDF, email, and audit reference.

## Related feature files
- [[10-modules/receipts/features/receipt-generation/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-generation/overview]], then before [[application]], [[api]], and [[validations]].
