<!--
meta:
  title: Sales POS / POS Checkout / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, pos-checkout, business-rules]
-->
> Hub: [[10-modules/sales-pos/features/pos-checkout/overview]]

# POS Checkout - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **POS Checkout** feature inside the **Sales POS** module.

## Core rules
- sale remains sale-only; returns and exchanges are separate documents
- cart total and payable amount must remain visible during checkout
- line pricing uses snapshot data at the time of sale completion

## Why these rules matter
Fast touchscreen-first checkout is one of the most important business requirements in the BRD.

## Related feature files
- [[10-modules/sales-pos/features/pos-checkout/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/catalog/features/variants/overview|Variants]]
- [[10-modules/pricing/features/price-lists/overview|Price Lists]]
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/receipts/features/receipt-generation/overview|Receipt Generation]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/pos-checkout/overview]], then before [[application]], [[api]], and [[validations]].
