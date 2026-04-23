<!--
meta:
  title: Catalog / Variants / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, variants, validations]
-->

# Variants - Validations

Back to [[overview]]

## Purpose
This file defines input, business, and workflow validations for **Variants**.

## Input and business validations
- productId and sku required
- barcode optional but unique
- selected attribute values must belong to declared attributes
- limits must be positive when present

## Common validation split
- request shape validation at the API boundary
- business validation in the `Application` layer
- stable invariants in the `Domain` layer where relevant
- same-tenant checks before any create, update, or linkage action

## Workflow validations
- block duplicate active records or invalid primary-flag combinations
- block status transitions that would break active operational usage without a controlled path
- block cross-feature links when parent/child relationships are inconsistent

## Related files
- [[business-rules]]
- [[data-model]]
- [[application]]
- [[08-backend/validation-rules]]
