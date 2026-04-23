<!--
meta:
  title: Feature Template - Backend
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, backend, implementation]
-->

# Feature Backend Template

## Purpose of this file

Use this file to document **feature-specific backend implementation direction**.

This file should explain how the feature is implemented in backend terms beyond the shared project-wide backend rules.

## What belongs here

Include details such as:

- module-level backend responsibilities
- controllers, handlers, services, repositories, or integration touchpoints relevant to the feature
- transaction-sensitive backend behavior
- background or asynchronous processing only if it truly exists
- where the feature needs special backend handling beyond the shared rules
- implementation-sensitive notes that matter for maintainability

## What should not be duplicated here

Do not repeat the shared backend rules from:

- [../../../../07-backend/clean-architecture-rules.md](../../../../07-backend/clean-architecture-rules.md)
- [../../../../07-backend/application-layer-rules.md](../../../../07-backend/application-layer-rules.md)
- [../../../../07-backend/domain-layer-rules.md](../../../../07-backend/domain-layer-rules.md)
- [../../../../07-backend/infrastructure-layer-rules.md](../../../../07-backend/infrastructure-layer-rules.md)

Link to those rules and describe only what is feature-specific.

## Before filling this file, read

- [application.md](./application.md)
- [data-model.md](./data-model.md)
- [api.md](./api.md)
- [../../../../07-backend/backend-overview.md](../../../../07-backend/backend-overview.md)
- [../../../../07-backend/backend-folder-structure.md](../../../../07-backend/backend-folder-structure.md)

## Project-specific guidance

Use this file when the feature has important backend implementation behavior such as:

- tenant-aware query and write handling
- repository and Unit of Work coordination
- external provider or integration use
- stock, payment, or document state side effects
- retry, conflict, or exception behavior
- module boundary decisions

If the feature is simple and all relevant detail already lives in `application.md`, `api.md`, and `data-model.md`, keep this file short.

## Recommended structure

## Backend summary

Describe how the feature is implemented on the backend.

## Main backend components

| Component type | Example name | Responsibility |
|---|---|---|
| `[controller/service/repository]` | `[name]` | `[responsibility]` |

## Query / write responsibilities

Document where reads and writes happen and why.

## Transaction and persistence notes

Use when the feature has meaningful commit/rollback or persistence behavior.

## Integration notes

Use only if the feature touches providers, external services, or infrastructure-specific services.

## Performance / safety notes

Use only if the feature has special backend sensitivity.

## Related files

- [application.md](./application.md)
- [api.md](./api.md)
- [edge-cases.md](./edge-cases.md)
- [../../../../07-backend/repository-rules.md](../../../../07-backend/repository-rules.md)
- [../../../../07-backend/exception-handling-rules.md](../../../../07-backend/exception-handling-rules.md)

## Final check before saving

Confirm that this file:

- documents feature-specific backend direction only
- does not duplicate the shared backend standards
- stays aligned with module boundaries and transaction rules
- is useful for implementation and troubleshooting
