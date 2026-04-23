<!--
meta:
  title: Tax / Tax Rates / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-rates, validations]
-->
> Hub: [[10-modules/tax/features/tax-rates/overview]]

# Tax Rates - Validations

## Purpose
This file records input, business, and **workflow** validations for **Tax Rates**.

## Validation rules
- validate rate, tax_type, applies_to, country_code, and effective window

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/tax/features/tax-classes/overview|Tax Classes]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]
- [[10-modules/orders-ecommerce/features/orders/overview|Orders]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
