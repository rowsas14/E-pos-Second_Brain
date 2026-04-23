<!--
meta:
  title: Catalog / Brands / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, brands, backend]
-->

# Brands - Backend

Back to [[overview]]

## Purpose
This file explains backend implementation expectations for **Brands**.

## Backend design direction
- keep controllers thin and feature-grouped under the API layer
- orchestrate use cases in the `Application` layer
- preserve pure business meaning in `Domain`
- keep repository and persistence implementation in `Infrastructure`
- enforce tenant-safe access in every retrieval and mutation path

## Expected backend components
- Brand entity or aggregate root in catalog domain
- application service for create/update/activate/deactivate
- tenant-aware brand repository and duplicate-check query

## Implementation notes
- use `.NET Clean Architecture`
- use `EF Core` + `PostgreSQL`
- avoid direct `DbContext` usage from controllers or application services
- use feature-specific repositories and validators instead of vague generic abstractions
- keep catalog master-data mutations auditable when they affect operational behavior

## Related files
- [[application]]
- [[data-model]]
- [[08-backend/backend-overview]]
- [[08-backend/repository-rules]]
- [[08-backend/validation-rules]]
