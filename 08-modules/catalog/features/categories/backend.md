<!--
meta:
  title: Catalog / Categories / Backend
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-18
  tags: [catalog, categories, backend]
-->

# Categories - Backend

Back to [[overview]]

## Purpose
This file explains backend implementation expectations for **Categories**.

## Backend design direction
- keep controllers thin and feature-grouped under the API layer
- orchestrate use cases in the `Application` layer
- preserve pure business meaning in `Domain`
- keep repository and persistence implementation in `Infrastructure`
- enforce tenant-safe access in every retrieval and mutation path

## Expected backend components
- Category aggregate with parent-child integrity rules
- category tree query/read model
- category-attribute mapping service

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
