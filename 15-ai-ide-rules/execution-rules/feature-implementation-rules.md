<!--
meta:
  title: Feature Implementation Rules
  owner: Architecture Team
  status: active
  last_reviewed: 2026-04-18
  tags: [execution-rules, feature-implementation, ai-ide, workflow]
-->

# Feature Implementation Rules

Back to [[../README]]

## Purpose

This file defines how a feature must be implemented in the Unified Commerce platform.

It is not a coding style note.
It is the working rule set for turning business documentation into safe backend and frontend delivery.

Use this file before implementing any new feature or major feature change.

## Why this file exists

This platform is not a simple CRUD product.

A single feature can affect:
- tenant isolation
- POS flow
- E-Commerce flow
- `variant`-level selling
- stock movement and reservation
- payment capture and allocation
- returns and exchanges
- permissions and approvals
- reporting and auditability

If implementation starts directly from code without reading the correct docs, the result may compile but still be wrong.

## Core project truths that every implementation must respect

Every feature implementation must preserve these rules:

- platform admin is separate from tenant staff
- tenant staff belong to exactly one tenant
- customers are tenant-specific
- memberships are tenant-specific
- sellable transaction behavior uses `variant` level identity
- inventory uses `stock_movements` plus `inventory_balances`
- payments are unified, but allocations remain explicit
- returns and exchanges are separate business documents
- POS and E-Commerce share foundations but not identical workflows
- sensitive actions must remain permission-aware and auditable

If a feature breaks one of these truths, the implementation is wrong.

## Rule 1: never start coding first

Before writing code:
- identify the target module and feature
- identify whether the change is small, medium, or high-risk
- read the required documents
- summarize the business flow
- identify rules, validations, and dependencies
- only then start implementation

Do not start from controller, table, or UI guesswork.

## Rule 2: classify the feature before reading

### Small feature
Use this when:
- one feature only
- no major workflow change
- no major DB/API impact
- low risk

Examples:
- one validation addition
- one response field addition
- one minor backend change

### Medium feature
Use this when:
- one main feature plus related dependencies
- DB or API impact exists
- business rules matter
- moderate workflow impact exists

Examples:
- product create
- stock adjustment
- customer create
- tenant setting change

### High-risk feature
Use this when:
- payment, stock, return, exchange, checkout, order placement, or permission model is affected
- cross-module impact exists
- transaction-sensitive behavior exists
- audit-sensitive behavior exists

Examples:
- POS checkout
- refund
- return processing
- exchange completion
- payment allocation
- stock reservation release

## Rule 3: required reading order by risk level

### For small feature
Read:
1. target feature `overview.md`
2. target feature `business-rules.md`
3. target feature `backend.md`
4. target feature `validations.md`
5. target feature `api.md` if API changes
6. target feature `data-model.md` if DB changes

### For medium feature
Read:
1. [[../../01-product/product-overview]]
2. [[../../02-domain/domain-overview]]
3. [[../../02-domain/tenancy-model]]
4. [[../../04-architecture/clean-architecture-rules]]
5. [[../../06-database/database-overview]]
6. [[../../06-database/tenant-scoping-rules]]
7. [[../../07-api/api-standards]]
8. [[../../08-backend/backend-overview]]
9. [[../../08-backend/layer-responsibilities]]
10. [[../../08-backend/application-layer-rules]]
11. target feature `overview.md`
12. target feature `business-rules.md`
13. target feature `data-model.md`
14. target feature `application.md`
15. target feature `api.md`
16. target feature `validations.md`
17. target feature `backend.md`

### For high-risk feature
Read:
1. [[../../01-product/product-overview]]
2. [[../../01-product/scope]]
3. [[../../02-domain/domain-overview]]
4. [[../../02-domain/tenancy-model]]
5. [[../../04-architecture/system-overview]]
6. [[../../04-architecture/unified-commerce-architecture]]
7. [[../../04-architecture/multi-tenant-architecture]]
8. [[../../04-architecture/clean-architecture-rules]]
9. [[../../06-database/database-overview]]
10. [[../../06-database/tenant-scoping-rules]]
11. [[../../06-database/entity-relationship-overview]]
12. [[../../07-api/api-overview]]
13. [[../../07-api/api-standards]]
14. [[../../07-api/error-contract]]
15. [[../../08-backend/backend-overview]]
16. [[../../08-backend/layer-responsibilities]]
17. [[../../08-backend/application-layer-rules]]
18. [[../../08-backend/repository-rules]]
19. [[../../08-backend/service-composition-rules]]
20. [[../../08-backend/validation-rules]]
21. [[../../08-backend/transaction-rules]]
22. target feature `overview.md`
23. target feature `business-rules.md`
24. target feature `data-model.md`
25. target feature `application.md`
26. target feature `api.md`
27. target feature `workflows.md`
28. target feature `permissions.md`
29. target feature `validations.md`
30. target feature `edge-cases.md`
31. target feature `backend.md`

## Rule 4: required analysis before implementation

Before coding, write down:

- feature summary
- affected modules
- entities/tables involved
- business rules
- validations
- tenant constraints
- API impact
- workflow impact
- permission impact
- audit impact
- unclear or missing documentation

If the docs are unclear, report the gap before coding.

## Rule 5: respect layer boundaries

### Presentation
Owns:
- controllers
- requests
- responses
- middleware handoff

Must not own:
- business orchestration
- repository-driven business flow
- payment or stock logic

### Application
Owns:
- use-case orchestration
- validator coordination
- transaction sequencing
- cross-module workflow coordination

### Domain
Owns:
- business meaning
- invariants
- aggregate rules
- pure domain logic

### Infrastructure
Owns:
- `EF Core`
- repositories
- persistence
- provider integrations
- technical adapters

If a feature implementation breaks this split, refactor it before considering the work complete.

## Rule 6: feature implementation must follow use-case flow, not table flow

Do not implement from table order.

Implement from business flow order.

Examples:
- checkout flow first, then supporting persistence
- refund policy first, then payment rows
- return/exchange business flow first, then ledger and allocation records

The business process decides code structure.
The table structure does not.

## Rule 7: tenant safety is mandatory in every feature

Every feature implementation must check:
- who is acting
- which tenant the actor belongs to
- whether target records belong to the same tenant
- whether outlet context belongs to that tenant
- whether customer context belongs to that tenant
- whether cross-tenant leakage is possible through ids, joins, or route access

Do not trust client-supplied tenant context blindly.

## Rule 8: `variant` rules must not be skipped

For sellable transaction flows:
- use `variantId`
- validate variant ownership
- validate variant sellability
- validate stock behavior at variant level
- validate pricing at variant level

Do not implement sellable flow with product-only shortcuts.

## Rule 9: reverse-flow rules must not be simplified

For:
- refunds
- returns
- exchanges

do not implement shortcuts such as:
- negative sale rows
- hidden order reversal
- direct payment row edit without allocation meaning

The project model is explicit:
- returns are separate
- exchanges are separate
- refunds are explicit
- allocations remain explicit

## Rule 10: validation must be split correctly

Use:
- input validation
- business validation
- workflow validation
- tenant-boundary validation
- domain invariant enforcement

Do not put all validation in one place.

## Rule 11: complex flows require service composition, not controller scripting

For flows such as:
- checkout
- refund
- return
- exchange
- order placement
- stock reservation release

the implementation must be coordinated through `Application` services.

Do not let controllers, repositories, or provider clients become the real workflow owner.

## Rule 12: required outputs after implementation

After code is done, list:

- created files
- updated files
- impacted modules
- test cases
- regression risk areas
- documentation files that must be updated

Implementation is incomplete without this impact list.

## Rule 13: required documentation updates after code

At minimum, check whether these files need updates:

- target feature `application.md`
- target feature `backend.md`
- target feature `api.md`
- target feature `validations.md`
- target feature `data-model.md`
- target feature `workflows.md`
- target feature `permissions.md`
- target feature `edge-cases.md`
- target feature `bugs.md` if defect-related
- target feature `changelog.md`

If shared behavior changed, also check:
- [[../../06-database/README]]
- [[../../07-api/README]]
- [[../../08-backend/README]]
- related ADR files

## Rule 14: done criteria

A feature is not done when code compiles.

A feature is done only when:
- business rules are respected
- tenant safety is preserved
- layer boundaries are respected
- validations are complete
- tests are added or updated
- impacted docs are updated
- changelog is updated where required

## Common mistakes to avoid

Do not:
- code before reading docs
- assume missing business rules
- skip tenant checks
- use product-level shortcuts where `variant` is required
- put business flow into controllers
- put business policy into repositories
- treat return as negative sale
- treat exchange as normal sale/order mutation
- forget doc updates after implementation

## Related files

- [[bug-fix-rules]]
- [[api-change-rules]]
- [[database-change-rules]]
- [[documentation-update-rules]]
- [[../../08-backend/service-composition-rules]]
- [[../../08-backend/validation-rules]]
- [[../../08-backend/transaction-rules]]

## Final note

This project must be implemented from business truth to code, not from code convenience to business interpretation.

If a feature implementation ignores this rule set, the result may look complete but will not be trustworthy.