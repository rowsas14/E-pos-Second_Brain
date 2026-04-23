<!--
meta:
  title: Frontend Architecture
  owner: Frontend / Architecture
  status: active
  last_reviewed: 2026-04-22
  tags: [architecture, frontend, react, typescript, tailwind, pos-ui]
-->

# Frontend Architecture

## Purpose

This document explains the frontend architecture direction for the Unified Commerce Platform based on the uploaded frontend architecture notes and the approved product and architecture model.

The frontend stack is:

- **React**
- **TypeScript**
- **Tailwind CSS**

## Frontend architecture direction

The uploaded notes organize the frontend into these main areas:

- `bootstrap`
- `core`
- `features`
- `shells`
- `pages`
- `state`
- `shared-kernel`

This structure is appropriate for the project because the frontend must support multiple operational experiences rather than one generic website:

- POS operation
- tenant/admin operation
- E-Commerce-related customer flows
- permissions and role-aware behavior
- tenant themes and configuration
- device and peripheral integration support for POS

## Practical layer interpretation

| Area from uploaded notes | Responsibility |
|---|---|
| `bootstrap` | app startup, router, guards, providers, main layouts |
| `core` | API client, auth/session handling, offline support, peripherals, config, utilities |
| `features` | business feature areas such as products, cart, payments, returns, inventory |
| `shells` | reusable composition shells for POS-facing operational screen sections |
| `pages` | route-level pages such as POS, payment, return, till open/close, dashboard |
| `state` | application and workflow state for session, till, cart, UI, offline behavior |
| `shared-kernel` | shared domain-like utilities such as money, tax, pricing, receipt or invoice engines |

## About app / core / shared / modules / widgets wording

The uploaded notes do not define an explicit `app`, `modules`, or `widgets` folder structure using those exact names.

In this project:

- `bootstrap` plays the practical role of the application startup layer
- `features` plays the role of the module-oriented UI layer
- `core` and `shared-kernel` together cover shared and cross-cutting frontend concerns
- `shells` act as reusable operational composition structures

A separate widget layer should not be invented unless the approved frontend structure is changed intentionally and documented. The current architecture should follow the uploaded structure instead of introducing a new naming model without need.

## Why this frontend cannot behave like a generic website

The source documents make the product direction very clear:

- POS is touchscreen-first
- POS is barcode-first and low-typing
- cashier speed matters
- visible totals and fast actions matter
- tenants can have tenant-specific themes and configuration
- role and capability behavior affects screen visibility and actions

So the frontend must be built as an **operational commerce interface**, not as a general marketing-style UI.

## POS support in the frontend structure

The uploaded notes directly support POS-oriented architecture through:

- POS layout separation
- till session guard
- role and auth guards
- cart, payments, returns, receipts, and till-session features
- POS-specific pages
- peripheral integration points such as printer, scanner, and cash drawer support
- state dedicated to session, till, cart, and offline behavior

This aligns well with the product requirement that POS be fast for cashiers and optimized for store operation.

## Admin and tenant support in the frontend structure

The frontend must also support non-cashier operational areas such as tenant administration and business configuration.

That means the frontend architecture must allow for:

- different layouts by operating context
- role-aware routes and screens
- tenant settings and UI theme application
- outlet-aware operation
- module-level separation between POS-facing and administrative workflows

## E-Commerce support in the frontend structure

The source material confirms that the platform includes E-Commerce alongside POS.

The frontend architecture should therefore remain capable of supporting:

- product discovery and product detail experiences
- cart and checkout behavior
- customer account behavior
- order status and customer-facing flows

But those flows must still follow the same product, tenancy, and shared-foundation rules defined across the project.

## Permissions and configuration behavior

Frontend architecture must not hard-code a single feature surface for all tenants.

It must support:

- route and screen guarding
- role-aware action visibility
- feature visibility shaped by capability assignment and configuration
- tenant theme application
- channel-appropriate behavior without breaking shared platform rules

## Relationship to backend and product model

The frontend should follow the real project model defined in:

- [../01-product/README.md](../01-product/README.md)
- [system-overview.md](./system-overview.md)
- [multi-tenancy-model.md](./multi-tenancy-model.md)
- [role-permission-capability-model.md](./role-permission-capability-model.md)

It should not create an easier but incorrect UX model that ignores tenant boundaries, feature governance, or POS operating needs.

## Related documents

- [system-overview.md](./system-overview.md)
- [role-permission-capability-model.md](./role-permission-capability-model.md)
- [../06-frontend/README.md](../06-frontend/README.md)
- [../06-frontend/pos-ui-principles.md](../06-frontend/pos-ui-principles.md)
- [../06-frontend/pos-screen-layout-rules.md](../06-frontend/pos-screen-layout-rules.md)
- [../06-frontend/tenant-theme-application.md](../06-frontend/tenant-theme-application.md)
