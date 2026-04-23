<!--
meta:
  title: Architecture Section README
  owner: Architecture / Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [architecture, unified-commerce, entry, system-design]
-->

# Architecture Documentation

## Purpose

This folder explains how the **Unified Commerce Platform** is structured at the system level.

The project is not a standalone POS application and it is not an e-commerce-only system. It is a **multi-tenant unified commerce platform** that combines **E-POS** and **E-Commerce** on one shared foundation while keeping platform administration, tenant operations, customer identity, configuration, and business documents properly separated.

Use this section to understand the architecture model before changing schema, API behavior, backend workflows, frontend structure, permissions, or tenant configuration.

## Why this section matters

For this project, architecture documentation is not optional background material.

Important platform rules affect almost every implementation decision:

- platform admin is separate from tenant staff
- staff users are tenant-bound
- customers and memberships are tenant-specific
- sellable flows operate at variant level
- inventory uses ledger + projection
- returns and exchanges are separate business documents
- POS is touchscreen-first, barcode-first, and low-typing
- each tenant operates its own customer-specific configuration
- feature access must be assignable by platform admin and configurable inside the customer tenant

If those rules are ignored, the system can drift into incorrect role logic, weak tenant isolation, duplicated business behavior, or a frontend/backend structure that behaves like a generic website instead of a unified commerce platform.

## What this folder covers

This section documents:

- the overall system shape
- the operating meaning of multitenancy
- the technical architecture direction for multitenancy
- the role, permission, and feature capability model
- backend architecture direction
- frontend architecture direction
- clean architecture rules
- practical scalability concerns

## Files in this folder

| File | Purpose |
|---|---|
| [system-overview.md](./system-overview.md) | practical view of how the full platform fits together |
| [multi-tenancy-model.md](./multi-tenancy-model.md) | explains what tenancy means in this platform from an operating-model perspective |
| [multi-tenant-architecture.md](./multi-tenant-architecture.md) | explains how multitenancy is enforced technically |
| [role-permission-capability-model.md](./role-permission-capability-model.md) | explains roles, permissions, feature capabilities, and tenant-side configuration |
| [backend-architecture.md](./backend-architecture.md) | explains the .NET Web API + Clean Architecture backend direction |
| [frontend-architecture.md](./frontend-architecture.md) | explains the React + TypeScript + Tailwind frontend direction |
| [clean-architecture-rules.md](./clean-architecture-rules.md) | defines practical Clean Architecture rules for this project |
| [scalability-considerations.md](./scalability-considerations.md) | explains where scale pressure is most likely to appear first |

## Read this section first when

Read this section before:

- creating or changing a module
- changing tenant boundaries or access control
- changing schema direction that affects tenant or document ownership
- changing backend layer responsibilities
- changing frontend structure or screen composition approach
- changing how permissions, feature availability, or tenant configuration work
- introducing reporting, payment, inventory, or other transaction-sensitive behavior that crosses modules

## Suggested reading order by task

### New to the project

1. [system-overview.md](./system-overview.md)
2. [multi-tenancy-model.md](./multi-tenancy-model.md)
3. [role-permission-capability-model.md](./role-permission-capability-model.md)
4. [backend-architecture.md](./backend-architecture.md)
5. [frontend-architecture.md](./frontend-architecture.md)
6. [clean-architecture-rules.md](./clean-architecture-rules.md)

### Working on tenant, role, or configuration behavior

1. [multi-tenancy-model.md](./multi-tenancy-model.md)
2. [multi-tenant-architecture.md](./multi-tenant-architecture.md)
3. [role-permission-capability-model.md](./role-permission-capability-model.md)
4. [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)
5. [../11-config-and-customization/README.md](../11-config-and-customization/README.md)

### Working on implementation structure

1. [backend-architecture.md](./backend-architecture.md)
2. [frontend-architecture.md](./frontend-architecture.md)
3. [clean-architecture-rules.md](./clean-architecture-rules.md)
4. [../07-backend/README.md](../07-backend/README.md)
5. [../06-frontend/README.md](../06-frontend/README.md)

### Working on scaling or performance-sensitive features

1. [system-overview.md](./system-overview.md)
2. [scalability-considerations.md](./scalability-considerations.md)
3. [../04-data/database-overview.md](../04-data/database-overview.md)
4. [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
5. relevant feature docs under [../08-modules/](../08-modules/README.md)

## Connected sections outside this folder

Architecture should be read together with:

- [../01-product/README.md](../01-product/README.md)
- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)
- [../04-data/README.md](../04-data/README.md)
- [../05-api/README.md](../05-api/README.md)
- [../06-frontend/README.md](../06-frontend/README.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../08-modules/README.md](../08-modules/README.md)

## Boundary of this folder

This folder explains **architecture direction and ownership boundaries**.

It should not become the place where detailed feature workflows, table-by-table schema design, or layer-specific coding rules are duplicated in full. When deeper detail is needed, link to the owning file in [../04-data/](../04-data/README.md), [../06-frontend/](../06-frontend/README.md), [../07-backend/README.md](../07-backend/README.md), or [../08-modules/README.md](../08-modules/README.md).
