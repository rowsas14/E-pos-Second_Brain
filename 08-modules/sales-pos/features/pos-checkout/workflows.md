<!--
meta:
  title: Sales POS / POS Checkout / Workflows
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, pos-checkout, workflows]
-->
> Hub: [[10-modules/sales-pos/features/pos-checkout/overview]]

# POS Checkout - Workflows

## Purpose
This file captures the operational **workflow** for **POS Checkout** across user, system, and integration steps.

## Main workflows
- scan or search variant
- edit cart line quantity/discount
- collect payment and complete sale

## Workflow dependencies
- [[business-rules]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[edge-cases]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/pos-checkout/overview]] and [[business-rules]]; combine with [[application]] for end-to-end implementation.
