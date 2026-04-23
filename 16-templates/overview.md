<!--
meta:
  title: Feature Template - Overview
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-23
  tags: [template, feature-docs, overview, module-docs]
-->

# Feature Overview Template

## Purpose of this file

Use this file as the **entry page** for one real feature under `08-modules/<module>/features/<feature>/`.

This file should help a reader understand, in one place:

- what the feature is
- why it exists in the Unified Commerce Platform
- who uses it
- where it fits in the module
- which deeper files must be read next

For most feature work, this should be the **first file read inside the feature folder**.

## What belongs here

Write only high-value summary information that helps someone orient themselves before opening the deeper files.

Include:

- feature name and one-sentence purpose
- owning module
- owning team or role
- primary actors, such as platform admin, tenant admin, cashier, manager, inventory staff, e-commerce staff, or customer
- high-level scope of the feature
- feature dependencies on other modules or platform rules
- important linked files in the same feature folder
- important project-level files that must be read with this feature

If the feature has a **default role mapping**, mention it only as a summary note here.

## What does **not** belong here

Do **not** turn this file into a duplicate of the other feature files.

Push the following into deeper files instead:

- detailed business constraints -> [business-rules.md](./business-rules.md)
- step-by-step user or system flows -> [workflows.md](./workflows.md)
- entity and field detail -> [data-model.md](./data-model.md)
- detailed request or rule checks -> [validations.md](./validations.md)
- role / permission / capability / effective access detail -> [permissions.md](./permissions.md)
- endpoint contracts -> [api.md](./api.md)
- application-layer orchestration -> [application.md](./application.md)
- backend implementation detail -> [backend.md](./backend.md)
- frontend interaction detail -> [frontend.md](./frontend.md)
- unusual cases and failure paths -> [edge-cases.md](./edge-cases.md)

## Before filling this file, read

At minimum:

- [../../01-product/README.md](../../01-product/README.md)
- [../../02-architecture/system-overview.md](../../02-architecture/system-overview.md)
- [../../02-architecture/multi-tenancy-model.md](../../02-architecture/multi-tenancy-model.md)
- [../../02-architecture/role-permission-capability-model.md](../../02-architecture/role-permission-capability-model.md)
- [../../03-decisions/ADR-index.md](../../03-decisions/ADR-index.md)

Read more depending on the feature:

- data-heavy feature -> [../../04-data/README.md](../../04-data/README.md)
- API-heavy feature -> [../../05-api/README.md](../../05-api/README.md)
- frontend-heavy feature -> [../../06-frontend/README.md](../../06-frontend/README.md)
- backend-heavy feature -> [../../07-backend/README.md](../../07-backend/README.md)
- config-heavy feature -> [../../11-config-and-customization/README.md](../../11-config-and-customization/README.md)
- security-sensitive feature -> [../../12-security-and-compliance/README.md](../../12-security-and-compliance/README.md)

## Project-specific guidance

This project is not a generic CRUD system. When summarizing a feature, reflect relevant project realities only when they actually apply:

- the platform combines E-POS and E-Commerce
- the system is multi-tenant
- platform admin is separate from tenant staff
- staff users are tenant-bound
- customers are tenant-specific
- sellable flows operate at variant level
- inventory uses ledger + projection
- returns and exchanges are separate documents
- POS flows prioritize barcode-first, low-typing, cashier speed
- feature access can be assigned by platform admin and configured in the tenant

Do not force every point into every feature. Include only what the feature truly depends on.

## Default role mapping note

If a feature is seeded with a default role, use one short summary line here only.

Good example:

- “This feature may be seeded with `manager` as a default role mapping during onboarding.”

Do **not** write the default role as if it were the final runtime rule. Document the effective access model in [permissions.md](./permissions.md).

## Recommended structure

## Feature summary

- **Feature name:** `[Feature Name]`
- **Module:** `[Module Name]`
- **Purpose:** `[One clear sentence about what this feature does]`

## Why this feature exists

Describe the business or operational need this feature solves inside the unified commerce platform.

## Primary actors

| Actor | How this actor uses the feature |
|---|---|
| `[Actor]` | `[Usage]` |

## High-level access note

Use this section only when the feature has a meaningful access model summary.

Example:
- `[Feature] may be seeded with [Role] by default, but final access is defined in permissions.md through platform-admin assignment and tenant configuration.`

## In scope for this feature

List what this feature directly owns.

## Out of scope for this feature

List nearby behaviors that belong to another feature or module.

## Dependencies

| Dependency type | Related item | Why it matters |
|---|---|---|
| Module | `[Related module/feature]` | `[Reason]` |
| Architecture rule | `[Rule]` | `[Reason]` |

## Read next

- [business-rules.md](./business-rules.md)
- [workflows.md](./workflows.md)
- [data-model.md](./data-model.md)
- [permissions.md](./permissions.md)

## Related project docs

- [../../02-architecture/system-overview.md](../../02-architecture/system-overview.md)
- [../../04-data/database-overview.md](../../04-data/database-overview.md)
- [../../05-api/api-overview.md](../../05-api/api-overview.md)
- [../../07-backend/backend-overview.md](../../07-backend/backend-overview.md)

## Final check before saving

Confirm that this file:

- helps a reader understand the feature in under a few minutes
- does not duplicate deep detail from other files
- does not mistake a default role mapping for final access
- links to the real next documents needed for implementation or QA
- stays aligned with the current project rules and module boundaries
