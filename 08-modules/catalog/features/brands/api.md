<!--
meta:
  title: Catalog / Brands / API
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, brands, api]
-->

# Brands - API

Back to [[overview]]

## Purpose
This file defines the feature-owned API surface for **Brands**.

## Current API boundary expectation
The exact endpoint set must stay aligned with shared rules in [[07-api/api-standards]]. For this feature, the expected resource family is:

- `/api/v1/catalog/brands`
- `/api/v1/catalog/brands/{id}`

## Contract direction
- use `/api/v1/...` route versioning
- keep routes resource-oriented
- enforce tenant-safe access server-side
- use request/response models, not persistence entities
- return standardized success and error envelopes

## Typical operations
- list and search feature records
- get one record
- create
- update
- activate/deactivate or archive where applicable

## API-specific notes
- this feature must never expose cross-tenant catalog records
- use `variantId` rather than `productId` in sellable transaction-related flows
- keep admin maintenance endpoints separate from storefront or POS consumption endpoints where workflow meaning differs

## Related files
- [[workflows]]
- [[permissions]]
- [[validations]]
- [[07-api/api-overview]]
- [[07-api/api-standards]]
- [[07-api/error-contract]]
