<!--
meta:
  title: Folder Structure Guide
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [folder-structure, project-map, navigation, 2nd-brain]
-->

# Folder Structure Guide

## Purpose

This guide explains how the cleaned 2nd Brain is organized and how each folder should be used.

The structure follows the actual needs of this project: a **multi-tenant unified commerce platform** with shared foundations for POS and E-Commerce, separated platform and tenant responsibilities, and module-level documentation for the main business areas.

## Structure principle

The structure is layered on purpose.

```text
00-start-here        -> how to use the documentation system
01-product           -> why the platform exists and what is in scope
02-architecture      -> system boundaries and operating models
03-decisions         -> major recorded decisions
04-data              -> schema and data-governance rules
05-07                -> API, frontend, backend standards
08-modules           -> module and feature documentation
10-16                -> cross-cutting guidance and templates
19-project-history   -> project-wide history
99-archive           -> retired or moved material
```

This is not arranged like source code. It is arranged so readers can move from **intent** to **design** to **implementation guidance** to **history and operations**.

## Top-level folders

| Folder | Purpose | What belongs here |
|---|---|---|
| `00-start-here/` | entry point for readers | navigation, documentation rules, reading order |
| `01-product/` | product and business intent | objectives, goals, scope |
| `02-architecture/` | architecture direction | system overview, tenancy model, capability model, scalability notes |
| `03-decisions/` | major design decisions | ADRs and ADR support files |
| `04-data/` | data and schema guidance | schema principles, migration strategy, naming, tenant-consistency rules |
| `05-api/` | API-wide standards | endpoint rules, request/response standards, error contract, idempotency, versioning |
| `06-frontend/` | frontend-wide standards | POS UI rules, layout rules, state rules, frontend testing direction |
| `07-backend/` | backend-wide standards | application, domain, infrastructure, repository, validation, mapping, transaction rules |
| `08-modules/` | detailed business module documentation | module-level and feature-level documents |
| `10-user-flows/` | cross-feature user flows | user journeys that cross module boundaries |
| `11-config-and-customization/` | tenant-facing configuration guidance | settings, themes, permissions, pricing and tax configuration |
| `12-security-and-compliance/` | platform-wide security rules | authentication, authorization, isolation, session and audit rules |
| `13-testing-quality/` | quality and release controls | test strategy, regression, readiness, bug handling |
| `14-delivery-and-operations/` | deployment and support operations | environment, deployment, monitoring, incidents, backups |
| `15-ai-ide-rules/` | AI-assisted working rules | safe-edit rules, implementation rules, documentation update rules |
| `16-templates/` | reusable document templates | API, backend, frontend, feature, workflow, ADR templates |
| `19-project-history/` | project-wide record | release notes, overall changelog, major incidents, migrations, breaking changes |
| `99-archive/` | archived material | retired or moved documentation |

## How folders connect

```text
00-start-here -> 01-product -> 02-architecture -> 03-decisions -> 04-data
                                              -> 05-api / 06-frontend / 07-backend
                                              -> 08-modules
08-modules -> 11-config-and-customization / 12-security-and-compliance / 13-testing-quality
08-modules -> 14-delivery-and-operations / 15-ai-ide-rules / 16-templates
all major changes -> 19-project-history
```

Use that map when deciding what to read first and where to write changes.

## How `08-modules/` is organized

`08-modules/` is the main working area for detailed system documentation.

Pattern:

```text
08-modules/
  <module>/
    features/
      <feature>/
        overview.md
        business-rules.md
        data-model.md
        api.md
        application.md
        backend.md
        frontend.md
        permissions.md
        validations.md
        workflows.md
        edge-cases.md
        bugs.md
        changelog.md
```

Not every feature must use every file, but this pattern shows the intended ownership model.

## Business modules currently present

| Module | What it groups |
|---|---|
| `catalog/` | products, variants, categories, brands, suppliers, product images, attributes |
| `customers/` | customer profiles, customer auth, customer addresses |
| `discounts-promotions/` | discount requests, discount applications, coupons |
| `fulfillment-logistics/` | delivery and fulfillment-related features |
| `identity-access/` | staff users, roles, permissions, outlet assignments |
| `inventory/` | stock ledger, reservations, transfers, stocktakes |
| `memberships/` | membership tiers and customer memberships |
| `orders-ecommerce/` | carts, orders, product reviews |
| `payments/` | payments, allocations, provider transactions, refunds |
| `platform-administration/` | platform users, tenant lifecycle, tenant onboarding |
| `pricing/` | price lists and outlet price overrides |
| `receipts/` | receipt generation and delivery |
| `reporting/` | reporting areas and reporting features |
| `returns-exchanges/` | returns and exchanges |
| `sales-pos/` | POS checkout, till sessions, hold/recall sales, cash movements |
| `settings-configuration/` | feature flags, tenant settings, UI themes |
| `tax/` | tax classes and tax rates |
| `tenant-management/` | tenants and outlets |

## Read here vs write here

| Task | Read first | Write or update here |
|---|---|---|
| understand project entry points | `00-start-here/` | `00-start-here/` only if navigation rules changed |
| update product goal or scope | `01-product/` | `01-product/` |
| change system boundary or operating model | `02-architecture/` and `03-decisions/` | owning file in `02-architecture/` and possibly ADRs |
| change schema or data rules | `04-data/` and feature `data-model.md` | `04-data/` and/or feature `data-model.md` |
| change API-wide standards | `05-api/` | `05-api/` |
| change one feature’s behavior | feature folder in `08-modules/` | that feature folder |
| change tenant-wide configuration guidance | `11-config-and-customization/` | `11-config-and-customization/` plus affected modules if needed |
| change security policy | `12-security-and-compliance/` | `12-security-and-compliance/` |
| add or update test expectations | `13-testing-quality/` and feature docs | `13-testing-quality/` and/or feature docs |
| record broad project impact | `19-project-history/` | `19-project-history/` |

## Cross-cutting folders vs module folders

Use this rule:

- if the topic belongs to one business area, place it in the module or feature folder
- if the topic applies across the whole platform, place it in a cross-cutting folder

Examples:

| Topic type | Preferred location |
|---|---|
| feature-specific workflow for POS checkout | `08-modules/sales-pos/features/pos-checkout/workflows.md` |
| platform-wide authorization model | `12-security-and-compliance/authorization-model.md` or related architecture docs |
| tenant-wide theme configuration approach | `11-config-and-customization/ui-themes.md` |
| schema naming policy | `04-data/naming-conventions.md` |
| API error format | `05-api/error-contract.md` |

## Common navigation paths

### Understand the product first

- [../01-product/README.md](../01-product/README.md)
- [../01-product/business-objectives.md](../01-product/business-objectives.md)
- [../01-product/project-scope.md](../01-product/project-scope.md)

### Understand design boundaries

- [../02-architecture/README.md](../02-architecture/README.md)
- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)
- [../04-data/README.md](../04-data/README.md)

### Work on a feature

- [../08-modules/README.md](../08-modules/README.md)
- relevant feature `overview.md`
- relevant feature `business-rules.md`
- relevant feature `data-model.md`
- relevant feature `workflows.md`
- then the relevant standards from `05`, `06`, `07`, `11`, `12`, or `13`

## Related documents

- [README.md](./README.md)
- [documentation-rules.md](./documentation-rules.md)
- [how-to-use-this-brain.md](./how-to-use-this-brain.md)
- [../08-modules/README.md](../08-modules/README.md)
