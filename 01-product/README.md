<!--
meta:
  title: Product Section README
  owner: Product / Architecture
  status: active
  last_reviewed: 2026-04-22
  tags: [product, unified-commerce, entry, business-intent]
-->

# Product Documentation

## Purpose

This folder defines the **product and business intent** of the Unified Commerce Platform.

The project is not a standalone POS application and it is not an e-commerce-only system. It is a **unified multi-tenant commerce platform** that combines **E-POS** and **E-Commerce** on one shared foundation. This section explains **why the platform exists**, **what business outcomes it must support**, and **what is currently inside and outside project scope**.

Use this section before making architecture, schema, API, frontend, backend, or QA decisions. It gives the business frame that the deeper technical folders must follow.

## Why this section matters

For this project, technical decisions cannot be separated from the operating model.

Important examples:

- platform administration is separate from tenant staff operations
- staff users are tenant-bound
- customers and memberships are tenant-specific
- sellable flows operate at variant level
- inventory follows ledger + projection rules
- returns and exchanges are separate business documents
- POS behavior is optimized for fast cashier operation
- each tenant can configure approved features inside its own boundary
- feature capability assignment is controlled from the platform side

Those rules have business meaning first. They should not be treated as random technical preferences.

## What this folder covers

This folder contains the business-level explanation of:

- the platform’s business problem
- the intended business outcomes
- the current project scope
- the product-level reading order for new contributors

It does **not** replace detailed technical documentation in:

- [../02-architecture/README.md](../02-architecture/README.md)
- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)
- [../04-data/README.md](../04-data/README.md)
- [../05-api/README.md](../05-api/README.md)
- [../06-frontend/README.md](../06-frontend/README.md)
- [../07-backend/README.md](../07-backend/README.md)
- [../08-modules/README.md](../08-modules/README.md)

## Files in this folder

| File | Purpose | Read when |
|---|---|---|
| [business-goal.md](./business-goal.md) | explains the retail problem and business need this platform is solving | you need to understand why the platform exists |
| [business-objectives.md](./business-objectives.md) | explains the intended business and operating outcomes | you need to align design or implementation with target outcomes |
| [project-scope.md](./project-scope.md) | explains what is currently inside and outside scope | you need to decide whether a request belongs in the project |
| [README.md](./README.md) | section entry page and reading guide | you are entering the product section |

## Recommended reading order

### If you are new to the project

1. [business-goal.md](./business-goal.md)
2. [business-objectives.md](./business-objectives.md)
3. [project-scope.md](./project-scope.md)
4. [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
5. [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
6. [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)

### If you are implementing or changing a feature

Read this folder when the task affects:

- scope interpretation
- business rules
- tenant operating boundaries
- role and capability behavior
- cashier workflow priorities
- reporting expectations
- returns, exchanges, or payment handling direction

Then continue into:

- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../08-modules/README.md](../08-modules/README.md)

## Who should read this section

| Role | Why this section matters |
|---|---|
| Developer | prevents implementing technically correct but business-wrong behavior |
| Architect | anchors system boundaries in approved product intent |
| QA | clarifies expected business outcomes and scope boundaries |
| AI assistant | reduces unsupported assumptions and generic output |
| Delivery or product stakeholder | keeps conversations grounded in approved platform direction |

## Relationship to the rest of the 2nd Brain

```text
00-start-here -> 01-product -> 02-architecture -> 03-decisions -> 04-data
                                             -> 05-api / 06-frontend / 07-backend
                                             -> 08-modules
```

This folder should be read early, but it should stay focused on business intent. Detailed implementation rules belong in later sections.

## Related documents

- [../00-start-here/README.md](../00-start-here/README.md)
- [../00-start-here/how-to-use-this-brain.md](../00-start-here/how-to-use-this-brain.md)
- [business-goal.md](./business-goal.md)
- [business-objectives.md](./business-objectives.md)
- [project-scope.md](./project-scope.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
