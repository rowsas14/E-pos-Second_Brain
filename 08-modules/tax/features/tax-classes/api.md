<!--
meta:
  title: Tax / Tax Classes / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tax, tax-classes, api]
-->
> Hub: [[10-modules/tax/features/tax-classes/overview]]

# Tax Classes - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Tax Classes**.

## Endpoints / contract areas
- POST /tax/classes
- PATCH /tax/classes/{taxClassId}
- GET /tax/classes

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/tax/features/tax-classes/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/catalog/features/products/overview|Products]]
- [[10-modules/tax/features/tax-rates/overview|Tax Rates]]

## Recommended reading order
Read after [[10-modules/tax/features/tax-classes/overview]], [[business-rules]], [[data-model]], and [[application]].
