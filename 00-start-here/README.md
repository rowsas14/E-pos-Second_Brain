<!--
meta:
  title: 2nd Brain Start Here
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [start-here, unified-commerce, navigation, project-entry]
-->

# 2nd Brain Start Here

## Purpose

This folder is the entry point to the project’s 2nd Brain for the **Unified Commerce Platform**.

This platform combines **E-POS** and **E-Commerce** on one shared multi-tenant foundation. The documentation here exists so product intent, architecture boundaries, schema direction, module behavior, implementation rules, and project history can stay aligned during real delivery work.

This is not a generic note vault. It is a working documentation system for a platform with these core characteristics:

- multi-tenant operation
- platform administration separated from tenant staff operations
- tenant-bound staff users
- tenant-specific customers and memberships
- variant-level sellable flows
- inventory modeled with ledger + projection
- returns and exchanges modeled as separate business documents
- touchscreen-first, barcode-first, low-typing POS workflows
- customer-specific tenant configuration
- platform-controlled feature assignment with tenant-side configuration

## Why this documentation exists

Without a structured 2nd Brain, the same rule gets rewritten in many places, business and technical documents drift apart, and feature work starts from incomplete assumptions.

This documentation exists to help the team:

- understand what the platform is supposed to do before building it
- keep product, schema, permissions, and implementation decisions consistent
- identify the correct source document before changing code or documentation
- onboard developers, QA, architects, and AI assistants faster
- reduce rework caused by cross-tenant, cross-module, or cross-layer misunderstandings

## Who this helps

| Role | How this 2nd Brain helps |
|---|---|
| Developers | find the right rules before changing API, UI, schema, or backend behavior |
| Architects | keep business intent, boundaries, ADRs, and implementation guidance aligned |
| QA | trace expected behavior, workflows, permissions, and edge cases |
| AI assistants | read the right documents first and avoid inventing unsupported behavior |
| Product and delivery stakeholders | verify scope, decisions, and platform constraints in one place |

## What belongs in this vault

This vault should contain project knowledge that supports design, implementation, testing, delivery, and maintenance.

That includes:

- product goals, business objectives, and scope
- architecture boundaries and operating models
- ADRs for important design decisions
- schema and data-governance rules
- API, frontend, and backend standards
- module and feature documentation
- configuration, security, testing, and operational guidance
- templates and project-wide history

This folder itself should only contain **entry guidance** and **navigation rules**.

## Start here first

Read these files in this order:

1. [documentation-rules.md](./documentation-rules.md)
2. [folder-structure-guide.md](./folder-structure-guide.md)
3. [how-to-use-this-brain.md](./how-to-use-this-brain.md)

Then move to:

- [../01-product/README.md](../01-product/README.md)
- [../01-product/business-objectives.md](../01-product/business-objectives.md)
- [../01-product/Bussines-goal.md](../01-product/Bussines-goal.md)
- [../01-product/project-scope.md](../01-product/project-scope.md)

Then continue with:

- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)

## Recommended reading path

```text
00-start-here/
  -> 01-product/
  -> 02-architecture/
  -> 03-decisions/
  -> 04-data/
  -> 05-api/ 06-frontend/ 07-backend/
  -> 08-modules/
  -> 11-19 cross-cutting folders
```

Use that path when you are new to the project or when the task affects multiple layers.

## Where to go next by need

| Need | Read first |
|---|---|
| Product intent and business meaning | [../01-product/README.md](../01-product/README.md) |
| System and tenancy boundaries | [../02-architecture/README.md](../02-architecture/README.md) |
| Major design decisions | [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md) |
| Schema and tenant-consistency rules | [../04-data/README.md](../04-data/README.md) |
| API-wide implementation rules | [../05-api/README.md](../05-api/README.md) |
| Frontend and POS behavior standards | [../06-frontend/README.md](../06-frontend/README.md) |
| Backend and transaction handling standards | [../07-backend/README.md](../07-backend/README.md) |
| Feature-level working documentation | [../08-modules/README.md](../08-modules/README.md) |
| Tenant configuration and customization | [../11-config-and-customization/README.md](../11-config-and-customization/README.md) |
| Security and compliance rules | [../12-security-and-compliance/README.md](../12-security-and-compliance/README.md) |
| Testing and release quality | [../13-testing-quality/README.md](../13-testing-quality/README.md) |
| Operations and support guidance | [../14-delivery-and-operations/README.md](../14-delivery-and-operations/README.md) |
| AI-assisted working rules | [../15-ai-ide-rules/README.md](../15-ai-ide-rules/README.md) |
| Templates for new docs | [../16-templates/README.md](../16-templates/README.md) |
| Project-wide history | [../19-project-history/overall-changelog.md](../19-project-history/overall-changelog.md) |

## What this folder should not hold

Do not place detailed business rules, schema definitions, API contracts, frontend behavior, backend implementation notes, or bug analysis here when those belong in deeper folders.

If a document explains how the platform works in detail, it probably belongs outside `00-start-here/`.

## Related documents

- [documentation-rules.md](./documentation-rules.md)
- [folder-structure-guide.md](./folder-structure-guide.md)
- [how-to-use-this-brain.md](./how-to-use-this-brain.md)
- [../01-product/README.md](../01-product/README.md)
- [../02-architecture/README.md](../02-architecture/README.md)
