<!--
meta:
  title: Tax / Tax Classes / Edge Cases
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, edge-cases]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - Edge Cases

## Purpose
This file captures uncommon, exception, and failure conditions for **Tax Classes**.

## Edge cases
- tax class changed after products already actively selling

## Why this matters
These are the scenarios most likely to break a happy-path implementation even when normal **workflow** and **validation** logic look correct.

## Related feature files
- [[10-modules/tax/features/tax-classes/overview]]
- [[workflows]]
- [[validations]]
- [[bugs]]
- [[backend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after the core feature files when handling exceptions, bugs, or production incidents.
