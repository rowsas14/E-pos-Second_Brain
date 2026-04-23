<!--
meta:
  title: Backend Architecture
  owner: Backend / Architecture
  status: active
  last_reviewed: 2026-04-22
  tags: [architecture, backend, dotnet, clean-architecture, modules]
-->

# Backend Architecture

## Purpose

This document explains the backend architecture direction for the Unified Commerce Platform based on the uploaded backend architecture notes and the approved project model.

The backend stack is:

- **.NET Web API**
- **Clean Architecture**
- **PostgreSQL with EF Core**

## Architecture direction

The backend follows a layered architecture with feature grouping inside the solution structure.

The uploaded notes show these main layers:

- **API / Presentation**
- **Application**
- **Domain**
- **Infrastructure**

That direction is compatible with the project’s needs because the platform has clear business rules, tenant-aware validation, transaction-sensitive workflows, and cross-channel shared foundations.

## Layer responsibilities

| Layer | Main responsibility |
|---|---|
| API / Presentation | controllers, request/response models, middleware, filters, API-facing composition |
| Application | use-case orchestration, workflow coordination, validators, DTOs, interfaces, strategy selection |
| Domain | core business entities, value objects, aggregates, domain rules |
| Infrastructure | persistence, repository implementations, external services, transaction support |

## API / Presentation layer

The uploaded backend notes organize API concerns around feature-based modules such as `Auth`, `Products`, `Orders`, `Payments`, and `Customers`.

The API layer contains:

- controllers
- request models
- response models
- middleware
- filters
- extensions and startup wiring

The API layer should expose the platform safely, but it should not become the place where business rules or tenant-consistency rules are decided.

## Application layer

The uploaded notes show the Application layer as the main place for use-case orchestration.

Examples from the notes include:

- services
- validators
- DTOs
- interfaces
- strategies and factories where business behavior switches are needed

This is the correct place for:

- coordinating use cases
- calling repositories and services through abstractions
- enforcing workflow-level validation
- handling transaction-sensitive orchestration
- mapping domain outcomes into application-facing results

## Domain layer

The uploaded notes show a pure Domain layer with entities such as products, orders, payments, customers, and inventory-related models.

The Domain layer should contain:

- business entities and aggregates
- value objects and enums where appropriate
- domain rules that should not depend on API or database concerns
- domain services when a rule does not belong to one entity alone

This matters for the project because rules such as variant-level selling, document separation for returns/exchanges, or inventory movement semantics should not be scattered through controllers.

## Infrastructure layer

The uploaded notes place database access and integrations in Infrastructure.

That includes:

- persistence
- repository implementations
- external services
- unit of work or transaction support

Infrastructure is where EF Core and PostgreSQL-specific implementation belongs. It should not define business meaning, but it is responsible for persisting and retrieving data in a way that respects the project’s tenant and transaction rules.

## Feature-based organization

The uploaded backend notes group features by module area rather than one flat layer-wide folder.

That is directionally correct, but the full implementation must align with the larger project model, which goes beyond the sample notes and includes areas such as:

- platform administration
- tenant management
- identity and access
- catalog and pricing
- inventory
- POS sales
- E-Commerce orders
- payments and refunds
- returns and exchanges
- reporting
- settings and configuration

So the sample backend structure is a good pattern, but the final backend organization should align with the full module structure documented in [../08-modules/README.md](../08-modules/README.md).

## Tenant and workflow alignment expectations

The backend architecture must stay aligned with project-wide rules:

- staff are tenant-bound
- customers are tenant-specific
- operational transactions belong to exactly one tenant
- feature access is capability-governed and tenant-configurable
- inventory uses ledger + projection
- payments, refunds, returns, and exchanges are transaction-sensitive flows

That means backend services cannot treat tenant filtering, permission validation, payment allocation, or stock movement posting as optional details.

## Transaction-sensitive workflows

The backend is especially important in these areas:

- POS sale completion
- order creation and reservation handling
- payment and allocation flows
- refunds
- stock movement posting
- return and exchange processing
- discount approvals and other sensitive actions

Those workflows should be coordinated in Application while keeping domain rules and infrastructure responsibilities separated.

## Relationship to other documentation

Read this file together with:

- [clean-architecture-rules.md](./clean-architecture-rules.md)
- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)

## Boundary of this file

This file explains the **backend architecture direction**.

Detailed coding rules, mapping rules, validation rules, and transaction-handling details should be maintained in [../07-backend/](../07-backend/README.md).
