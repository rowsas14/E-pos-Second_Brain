<!--
meta:
  title: Catalog / Products / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, products, validations]
-->

# Products - Validations

Back to [[overview]]

## Purpose
This file defines input, business, and workflow validations for **Products**.

## Input and business validations
- name, slug, productType, returnPolicyType required
- channel sellability must align with actual variant readiness
- same-tenant references for category/brand/tax class

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
