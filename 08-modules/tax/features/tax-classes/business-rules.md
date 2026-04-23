<!--
meta:
  title: Tax / Tax Classes / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, business-rules]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Tax Classes** feature inside the **Tax** module.

## Core rules
- tax class code unique within tenant
- tax class can apply to goods, services, shipping, or mixed

## Why these rules matter
Product-level tax assignment needs a business-friendly abstraction separate from raw tax rates.

## Related feature files
- [[10-modules/tax/features/tax-classes/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-classes/overview]], then before [[application]], [[api]], and [[validations]].
