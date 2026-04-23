<!--
meta:
  title: Feature Template - Application
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, application-layer, orchestration]
-->

# Feature Application Template

## Purpose of this file

Use this file to document the feature’s **Application-layer orchestration**.

This file should describe how the feature is coordinated in the Application layer:

- use cases
- application services
- service interfaces
- DTOs
- validators
- transaction coordination
- cross-repository or cross-module orchestration
- sequencing between domain, infrastructure, and response output

## What belongs here

Include:

- use-case level flow
- application service responsibilities
- interface boundaries when relevant
- action-specific DTO usage
- validator usage
- Unit of Work coordination when relevant
- where the feature calls repositories or other services
- transaction-sensitive orchestration notes

## What should not be written here

Do not use this file for:

- raw entity design -> [data-model.md](./data-model.md)
- deep infrastructure implementation detail -> [backend.md](./backend.md)
- generic backend rules -> [../../../../07-backend/application-layer-rules.md](../../../../07-backend/application-layer-rules.md)
- frontend screen behavior -> [frontend.md](./frontend.md)

## Before filling this file, read

- [overview.md](./overview.md)
- [business-rules.md](./business-rules.md)
- [validations.md](./validations.md)
- [api.md](./api.md)
- [../../../../07-backend/application-layer-rules.md](../../../../07-backend/application-layer-rules.md)
- [../../../../07-backend/dto-handling-rules.md](../../../../07-backend/dto-handling-rules.md)
- [../../../../07-backend/mapping-rules.md](../../../../07-backend/mapping-rules.md)

## Project-specific guidance

For this project, this file is especially important when the feature involves:

- multi-step workflows
- role or permission-sensitive orchestration
- payment or refund coordination
- stock movement or reservation effects
- return/exchange document linkage
- audit or reporting side effects
- tenant configuration affecting execution

## Recommended structure

## Application summary

Describe what the Application layer coordinates for this feature.

## Main use cases

| Use case | Purpose | Primary service/interface | Transaction-sensitive |
|---|---|---|---|
| `[name]` | `[purpose]` | `[service]` | `[yes/no]` |

## Service flow

Describe the orchestration sequence at a practical level.

## Interfaces

List service interfaces, repository interfaces, or Unit of Work contracts only when relevant.

## DTOs used by this feature

List action-specific DTOs such as create/update/response/list DTOs when relevant.

## Validation and mapping notes

Summarize how validators and mappers support this feature.

## Transaction coordination

Use only when the feature needs coordinated commit/rollback behavior.

## Related files

- [backend.md](./backend.md)
- [data-model.md](./data-model.md)
- [validations.md](./validations.md)
- [../../../../07-backend/service-layer-rules.md](../../../../07-backend/service-layer-rules.md)
- [../../../../07-backend/transaction-handling-rules.md](../../../../07-backend/transaction-handling-rules.md)

## Final check before saving

Confirm that this file:

- explains Application-layer behavior, not generic backend theory
- uses action/use-case language
- makes interfaces, DTOs, and orchestration visible where relevant
- stays aligned with the shared backend rules
