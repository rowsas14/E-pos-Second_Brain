<!--
meta:
  title: Tax / Tax Classes / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, validations]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Validations

## Purpose
This file records input, business, and **workflow** validations for **Tax Classes**.

## Validation rules
- reject duplicate code within tenant
- validate applies_to value

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
