<!--
meta:
  title: Bug Fix Rules
  owner: Architecture Team
  status: active
  last_reviewed: 2026-04-18
  tags: [execution-rules, bug-fix, troubleshooting, ai-ide, workflow]
-->

# Bug Fix Rules

Back to [[../README]]

## Purpose

This file defines how bugs must be investigated and fixed in the Unified Commerce platform.

It is not a generic debugging note.
It is the working rule set for fixing defects safely in a system that includes:
- multi-tenant E-POS and E-Commerce
- tenant-bound staff and tenant-specific customers
- `variant`-level transaction behavior
- stock movement ledger plus balance projection
- unified payments with explicit allocations
- separate return and exchange documents

Use this file before fixing any defect.

## Why this file exists

A bug in this project is rarely “just one line wrong”.

A defect may affect:
- tenant isolation
- cashier checkout speed
- till/session correctness
- stock balances
- payment capture or refund correctness
- return or exchange correctness
- auditability
- reporting

If bug fixing starts from symptom patching only, the same defect will return in another form.

## Core project truths that every bug fix must preserve

Every bug fix must preserve these rules:

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

If a bug fix breaks one of these truths, the fix is wrong.

## Rule 1: do not code first

Before changing code:
- identify the affected module and feature
- describe expected behavior
- describe actual behavior
- reproduce the issue
- identify likely impact area
- read the required docs
- summarize the broken rule or broken flow

Do not start by editing code blindly.

## Rule 2: classify the bug before investigation

### Low-risk bug
Use when:
- one feature only
- no major workflow break
- no payment / stock / return / exchange impact
- no tenant leakage risk

Examples:
- wrong validation message
- response field missing
- one incorrect filter
- one non-critical state check

### Medium-risk bug
Use when:
- one core feature is broken
- business rule mismatch exists
- API or DB impact may exist
- moderate workflow impact exists

Examples:
- product create duplicate check not working
- stock adjustment validation missing
- wrong order status update
- wrong category / brand same-tenant validation

### High-risk bug
Use when:
- checkout, order placement, refund, return, exchange, payment, stock, or permission model is affected
- cross-module impact exists
- audit-sensitive behavior exists
- transaction-sensitive behavior exists
- tenant leakage is possible

Examples:
- checkout completes after till session is closed
- refund exceeds captured allocation
- stock reservation releases twice
- cross-tenant customer or product access is possible
- exchange completes without valid return source

## Rule 3: required reading order by bug risk

### For low-risk bug
Read:
1. target feature `overview.md`
2. target feature `business-rules.md`
3. target feature `validations.md`
4. target feature `backend.md`
5. target feature `bugs.md`
6. target feature `api.md` if API is involved
7. target feature `data-model.md` if DB is involved

### For medium-risk bug
Read:
1. [[feature-implementation-rules]]
2. [[../../02-domain/domain-overview]]
3. [[../../02-domain/tenancy-model]]
4. [[../../06-database/database-overview]]
5. [[../../06-database/tenant-scoping-rules]]
6. [[../../08-backend/backend-overview]]
7. [[../../08-backend/application-layer-rules]]
8. [[../../08-backend/repository-rules]]
9. [[../../08-backend/validation-rules]]
10. target feature `overview.md`
11. target feature `business-rules.md`
12. target feature `workflows.md`
13. target feature `validations.md`
14. target feature `backend.md`
15. target feature `bugs.md`

### For high-risk bug
Read:
1. [[feature-implementation-rules]]
2. [[../../01-product/product-overview]]
3. [[../../02-domain/domain-overview]]
4. [[../../02-domain/tenancy-model]]
5. [[../../04-architecture/system-overview]]
6. [[../../04-architecture/multi-tenant-architecture]]
7. [[../../04-architecture/clean-architecture-rules]]
8. [[../../06-database/database-overview]]
9. [[../../06-database/tenant-scoping-rules]]
10. [[../../06-database/entity-relationship-overview]]
11. [[../../07-api/error-contract]]
12. [[../../08-backend/backend-overview]]
13. [[../../08-backend/application-layer-rules]]
14. [[../../08-backend/repository-rules]]
15. [[../../08-backend/service-composition-rules]]
16. [[../../08-backend/validation-rules]]
17. [[../../08-backend/transaction-rules]]
18. target feature `overview.md`
19. target feature `business-rules.md`
20. target feature `workflows.md`
21. target feature `validations.md`
22. target feature `edge-cases.md`
23. target feature `backend.md`
24. target feature `bugs.md`
25. target feature `api.md` if relevant
26. target feature `data-model.md` if relevant

## Rule 4: every bug investigation must produce these outputs first

Before fixing, write down:

- bug summary
- affected feature
- expected behavior
- actual behavior
- reproducible steps
- impacted modules
- broken business rule or workflow rule
- likely affected layer
- risk level
- missing or conflicting documentation

If documentation is unclear, report the gap before coding.

## Rule 5: find root cause, not only symptom

A valid bug investigation must identify:
- where the defect is visible
- where the defect is introduced
- why existing validation or workflow control failed
- whether the same defect can appear elsewhere

Examples:
- controller allows action but application service missed state check
- repository query loaded wrong tenant data
- business validation exists but workflow validation is missing
- refund calculation ignores previous refund allocations
- stock balance updated but stock movement not posted
- POS flow checks login but not open till session

Do not stop at “UI issue” or “API issue” unless that is truly the root cause.

## Rule 6: identify impacted layer before fixing

Check which layer is actually broken:

### Presentation
Examples:
- wrong request binding
- wrong error mapping
- wrong endpoint response shaping

### Application
Examples:
- use-case sequence wrong
- business validation missing
- workflow/state validation missing
- transaction orchestration broken

### Domain
Examples:
- invariant not protected
- state transition meaning too weak
- business rule expressed incorrectly

### Infrastructure
Examples:
- tenant-safe query missing
- wrong repository retrieval path
- persistence update not aligned with use case
- provider response handled incorrectly

Do not patch in the wrong layer just because it is faster.

## Rule 7: tenant leakage bugs are critical by default

If the defect allows:
- another tenant’s staff data to be seen
- another tenant’s customer to be loaded
- another tenant’s product / variant / price to be used
- another tenant’s payment / return / order / sale to be accessed

then the bug is automatically high-risk.

Fix rules:
- identify the missing same-tenant validation
- identify whether the bug is in query path, orchestration path, or auth boundary
- add regression coverage immediately
- review related features for the same pattern

## Rule 8: transaction-sensitive bugs must be fixed conservatively

Be extra careful when the bug affects:
- checkout
- order placement
- stock reservation / release
- stock movement posting
- payment capture
- refund execution
- return processing
- exchange completion

For these bugs:
- map the full flow first
- identify every affected record
- identify whether partial completion already happened
- avoid partial patch that hides deeper inconsistency

## Rule 9: validation bugs must be classified correctly

Split the broken validation into the right type:

- input validation
- business validation
- workflow validation
- tenant-boundary validation
- domain invariant protection

Examples:
- missing `variantId` → input validation
- refund exceeds refundable amount → business validation
- checkout after closed till session → workflow validation
- customer belongs to another tenant → tenant-boundary validation
- invalid payment direction meaning → domain invariant issue

Do not fix all validation bugs in one generic validator file without understanding the type.

## Rule 10: returns and exchanges must not be “simplified” during bug fixes

When fixing reverse-flow bugs:
- do not convert returns into negative sales
- do not convert exchanges into normal sale/order updates
- do not hide refund behavior inside generic payment edits
- preserve explicit return, exchange, refund, and allocation meaning

A shortcut fix here usually creates a bigger financial bug later.

## Rule 11: payment and allocation bugs require allocation-aware review

For bugs involving:
- payment capture
- sale allocation
- order allocation
- refund payout
- exchange difference collection/refund

always check:
- original payment direction
- captured amount
- already allocated amount
- already refunded amount
- idempotency / duplicate processing risk
- same-tenant linkage across records

Do not patch only the visible amount field.

## Rule 12: stock bugs require ledger-aware review

For bugs involving stock:
- check `stock_movements`
- check `inventory_balances`
- check reservation state
- check source workflow timing
- check whether the bug is visibility-only or truth-model corruption

Do not treat `inventory_balances` as the only stock truth.

## Rule 13: bug fixes must be minimal but complete

A good fix:
- changes the right layer
- fixes the actual rule/path that failed
- avoids unrelated refactor
- adds regression safety
- does not create new behavior drift

A bad fix:
- patches symptom only
- adds random checks in controllers
- duplicates business rules in multiple layers
- changes behavior without doc update

## Rule 14: every bug fix must produce regression tests

After fixing, add or update tests for:
- the reproduced bug path
- the main expected path
- the nearest related edge path
- tenant safety if relevant
- payment / stock / return / exchange safety if relevant

If the bug was high-risk, add at least one regression case for the surrounding workflow.

## Rule 15: every bug fix must update docs if behavior or rule changed

After the fix, check whether these need update:
- target feature `bugs.md`
- target feature `validations.md`
- target feature `workflows.md`
- target feature `backend.md`
- target feature `application.md`
- target feature `edge-cases.md`
- target feature `api.md` if response or failure behavior changed
- target feature `data-model.md` if persistence behavior changed
- target feature `changelog.md`

If shared rules changed, also check:
- [[../../07-api/error-contract]]
- [[../../08-backend/validation-rules]]
- [[../../08-backend/transaction-rules]]
- related ADR files

## Rule 16: bug fix done criteria

A bug fix is done only when:
- root cause is identified
- correct layer is fixed
- regression tests exist
- tenant safety is preserved
- payment / stock / reverse-flow safety is preserved if relevant
- docs are updated where needed
- `bugs.md` entry is updated with status / root cause / fix reference

## Common mistakes to avoid

Do not:
- code first without reading docs
- patch controller only for application-layer bugs
- add business policy into repository as a shortcut
- ignore tenant implications
- ignore allocation implications
- ignore stock ledger implications
- close bug without regression test
- close bug without updating `bugs.md` and `changelog.md` where needed

## Related files

- [[feature-implementation-rules]]
- [[database-change-rules]]
- [[documentation-update-rules]]
- [[../../08-backend/validation-rules]]
- [[../../08-backend/transaction-rules]]
- [[../../08-backend/exception-handling]]
- [[../../07-api/error-contract]]

## Final note

In this project, a bug fix is not successful because the visible error disappears.

A bug fix is successful only when the broken business rule, workflow rule, or tenant-safe execution rule is actually repaired without damaging the rest of the commerce model.