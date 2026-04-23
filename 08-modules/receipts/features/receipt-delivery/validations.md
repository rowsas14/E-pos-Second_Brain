<!--
meta:
  title: Receipts / Receipt Delivery / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-delivery, validations]
-->
> Hub: [[10-modules/receipts/features/receipt-delivery/overview]]

# Receipt Delivery - Validations

## Purpose
This file records input, business, and **workflow** validations for **Receipt Delivery**.

## Validation rules
- ensure receipt snapshot exists before delivery
- validate email destination when email delivery requested

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
