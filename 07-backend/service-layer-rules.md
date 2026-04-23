<!--
meta:
  title: Service Layer Rules
  owner: Backend Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [services, application-services, integration-services, interfaces]
-->

# Service Layer Rules

## Purpose

This file defines service design rules for the backend.

In this project, not every class named `Service` means the same thing. The documentation must distinguish between service types.

## Service types

| Service type | Layer | Purpose |
|---|---|---|
| application service | Application | orchestrates use cases and workflows |
| domain service | Domain | holds domain logic that does not fit one entity cleanly |
| infrastructure service | Infrastructure | implements technical integrations or provider-specific operations |

## Application services

Application services are the main use-case drivers.

Examples:
- product create/update workflows
- order progression workflows
- payment capture workflows
- return / exchange workflows
- tenant onboarding workflows

Rules:
- expose interfaces where the application contract matters
- remain module-aligned
- coordinate repositories, validators, and Unit of Work
- do not become generic “manager” classes for unrelated behaviors

## Domain services

Use domain services only when domain logic is real and not just orchestration.

## Infrastructure services

Infrastructure services implement technical integrations.

Examples:
- payment gateway client
- notification sender
- background integration adapter

Rules:
- hide provider-specific details
- implement interfaces where the application depends on them
- avoid carrying application workflow ownership

## Interface usage

Interfaces are appropriate for:

- application services consumed by API or orchestrating code
- repository contracts
- Unit of Work contract
- external service contracts

## Related documents

- [application-layer-rules.md](./application-layer-rules.md)
- [domain-layer-rules.md](./domain-layer-rules.md)
- [infrastructure-layer-rules.md](./infrastructure-layer-rules.md)
- [repository-rules.md](./repository-rules.md)
- [dto-handling-rules.md](./dto-handling-rules.md)
