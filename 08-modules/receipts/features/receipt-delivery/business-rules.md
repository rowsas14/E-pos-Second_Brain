<!--
meta:
  title: Receipts / Receipt Delivery / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, business-rules]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Receipt Delivery** feature inside the **Receipts** module.

## Core rules
- format_type can be thermal, pdf, email, or a4
- delivery retry should not create duplicate receipt numbers

## Why these rules matter
Generation and delivery have different failure modes and integrations, so they should be documented separately.

## Related feature files
- [[10-modules/receipts/features/receipt-delivery/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/receipts/features/receipt-delivery/overview]], then before [[application]], [[api]], and [[validations]].
