<!--
meta:
  title: Sales POS / Hold & Recall Sales / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, hold-recall-sales, business-rules]
-->
> Hub: [[10-modules/sales-pos/features/hold-recall-sales/overview]]

# Hold & Recall Sales - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Hold & Recall Sales** feature inside the **Sales POS** module.

## Core rules
- held sale is not a completed transaction
- held sale must retain cart state without posting final stock/payment effects as completed sale

## Why these rules matter
Real store counters need hold/recall for interrupted checkout, customer indecision, or queue management.

## Related feature files
- [[10-modules/sales-pos/features/hold-recall-sales/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]

## Recommended reading order
Read after [[10-modules/sales-pos/features/hold-recall-sales/overview]], then before [[application]], [[api]], and [[validations]].
