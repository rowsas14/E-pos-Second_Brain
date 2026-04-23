<!--
meta:
  title: Feature Template - Business Rules
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-23
  tags: [template, feature-docs, business-rules, domain-rules]
-->

# Feature Business Rules Template

## Purpose of this file

Use this file to document the **real business rules** for one feature.

This is where the feature’s operational truth should live:

- what is allowed
- what is disallowed
- what conditions must be checked
- what must happen before or after important actions
- what platform or tenant boundaries affect the feature

For business-heavy features, this file is one of the most important documents in the feature folder.

## What belongs here

Document rules such as:

- feature purpose from a business perspective
- eligibility or availability conditions
- state rules
- allowed transitions
- actor restrictions
- tenant, outlet, customer, or channel restrictions
- pricing, payment, stock, return, approval, or configuration constraints
- document linkage rules
- audit-sensitive behavior
- required approvals or manager intervention
- rules that distinguish POS, admin, manager, inventory, or e-commerce behavior

## What should **not** dominate this file

Do not let this file become:

- a UI step list -> use [workflows.md](./workflows.md)
- a backend class design note -> use [application.md](./application.md) or [backend.md](./backend.md)
- a field-by-field database description -> use [data-model.md](./data-model.md)
- a permission matrix only -> use [permissions.md](./permissions.md)
- a validation catalog only -> use [validations.md](./validations.md)

Short references are fine. Detailed ownership is not.

## Before filling this file, read

At minimum:

- [overview.md](./overview.md)
- [../../01-product/business-objectives.md](../../01-product/business-objectives.md)
- [../../01-product/business-goal.md](../../01-product/business-goal.md)
- [../../02-architecture/system-overview.md](../../02-architecture/system-overview.md)

Read these when relevant:

- tenant or role-sensitive feature -> [../../02-architecture/multi-tenancy-model.md](../../02-architecture/multi-tenancy-model.md), [../../02-architecture/role-permission-capability-model.md](../../02-architecture/role-permission-capability-model.md)
- stock-sensitive feature -> [../../04-data/schema-principles.md](../../04-data/schema-principles.md)
- payment-sensitive feature -> [../../05-api/idempotency-rules.md](../../05-api/idempotency-rules.md), [../../07-backend/transaction-handling-rules.md](../../07-backend/transaction-handling-rules.md)

## Project-specific guidance

This project often has rule-heavy features. When documenting business rules, actively check whether the feature depends on:

- tenant ownership
- outlet scope
- platform-admin assignment versus tenant-side configuration
- variant-level sellable behavior
- inventory movement or reservation effects
- return and exchange document separation
- approval-sensitive actions
- audit or reporting impact
- fast POS handling and low-typing cashier needs

Only include the items that truly apply to the feature.

## Default role mapping rule

If a feature has a default role mapping, capture it only when it affects the business meaning of the feature.

Examples:

- the feature is seeded to a common operational role at onboarding
- the business expects a default approval owner until the platform admin changes it

Do **not** write statements such as “this feature belongs to manager” unless the source material explicitly says the mapping is fixed and non-overridable.

Instead, use wording such as:

- “This feature may be seeded with `manager` as the default role mapping.”
- “Final access remains subject to platform-admin assignment and tenant-side configuration.”

Detailed runtime access belongs in [permissions.md](./permissions.md).

## Recommended structure

## Rule summary

Write 3-8 sentences describing the overall rule space for the feature.

## Rule catalog

| Rule ID | Rule | Why it exists | Related file |
|---|---|---|---|
| `BR-001` | `[Rule statement]` | `[Reason]` | `[Link if needed]` |

## Allowed behavior

List what actors or systems are allowed to do.

## Disallowed behavior

List what is explicitly not allowed.

## Preconditions

What must be true before this feature action can happen?

## Postconditions

What must be true after the action succeeds?

## State and transition rules

Use this section when the feature has meaningful statuses or business state.

## Tenant / outlet / channel considerations

Explain only when applicable.

## Approval / override rules

Use when manager approval, platform admin control, default role seeding, or tenant configuration affects the feature.

## Related files

- [workflows.md](./workflows.md)
- [validations.md](./validations.md)
- [permissions.md](./permissions.md)
- [data-model.md](./data-model.md)

## Final check before saving

Confirm that this file:

- contains real rules, not generic statements
- explains feature-specific business truth
- avoids implying that a default role is always the final role
- uses [permissions.md](./permissions.md) for effective access detail
- stays aligned with the approved product and architecture model
