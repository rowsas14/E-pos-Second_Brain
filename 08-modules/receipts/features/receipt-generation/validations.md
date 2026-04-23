<!--
meta:
  title: Receipts / Receipt Generation / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [receipts, receipt-generation, validations]
-->
> Hub: [[10-modules/receipts/features/receipt-generation/overview]]

# Receipt Generation - Validations

## Purpose
This file records input, business, and **workflow** validations for **Receipt Generation**.

## Validation rules
- ensure target document exists and belongs to tenant
- validate payload snapshot completeness before persist

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/returns-exchanges/features/returns/overview|Returns]]
- [[10-modules/returns-exchanges/features/exchanges/overview|Exchanges]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
