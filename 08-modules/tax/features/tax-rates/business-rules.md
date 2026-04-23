<!--
meta:
  title: Tax / Tax Rates / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, business-rules]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Tax Rates** feature inside the **Tax** module.

## Core rules
- unique code and starts_at combination within tenant
- effective-dated records determine correct applied rate at transaction time

## Why these rules matter
Actual percentage rates may change over time and need history-aware application.

## Related feature files
- [[10-modules/tax/features/tax-rates/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-rates/overview]], then before [[application]], [[api]], and [[validations]].
