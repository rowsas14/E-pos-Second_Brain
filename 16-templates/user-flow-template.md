<!--
meta:
  title: User Flow Template
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-23
  tags: [template, user-flow, workflow]
-->

# [Flow Title]

## Purpose
Use this file to document one real user flow for this project.

Write here:
- what business or operational outcome this flow supports
- whether the flow is for platform admin, tenant admin, cashier, manager, inventory staff, or e-commerce operations
- why this flow matters in the Unified Commerce platform

Do not write here:
- full feature specification
- API contract details
- backend class design
- detailed schema breakdown

If those details matter, link to the owning documents instead:
- [../feature-template/overview.md](./feature-template/overview.md)
- [../../05-api/README.md](../../05-api/README.md)
- [../../07-backend/README.md](../../07-backend/README.md)
- [../../04-data/README.md](../../04-data/README.md)

**Template:**

Flow purpose:

Flow type:
- [ ] Platform admin
- [ ] Tenant admin
- [ ] Cashier
- [ ] Manager
- [ ] Inventory staff
- [ ] E-commerce operations

Business outcome:

---

## Actor
Write the primary actor and any supporting actors.

Write here:
- who starts the flow
- who approves or intervenes
- which actions are done by a human and which are done by the system

Do not write here:
- permission rules in detail
- role-capability configuration logic in full

Link those instead:
- [../../02-architecture/role-permission-capability-model.md](../../02-architecture/role-permission-capability-model.md)
- [../../05-api/auth-and-authorization.md](../../05-api/auth-and-authorization.md)

**Template:**

Primary actor:

Supporting actors:
- User action:
- System action:

---

## Trigger
Write what starts the flow.

Write here:
- user intent
- starting screen/page/process
- event that begins the flow

Do not write here:
- all preconditions
- all branching logic

**Template:**

The flow starts when:

Start point:

---

## Preconditions
Write only the conditions that must already be true before the flow can begin.

Write here:
- session open / login present / tenant selected
- outlet selected
- required document or record exists
- required configuration already enabled

Do not write here:
- validations executed during the flow
- alternate steps

If preconditions depend on another document, link instead of repeating.

**Template:**

- 
- 
- 

---

## Main Flow
Write the normal happy-path flow as short numbered steps.

Rules:
- separate **actor actions** from **system actions** clearly
- keep POS flows fast and operational
- keep admin and e-commerce ops flows outcome-focused
- one step per action/result pair where possible

Do not write here:
- every UI pixel detail
- every backend process detail
- every validation rule in full

Link to feature docs when needed:
- [../feature-template/workflows.md](./feature-template/workflows.md)
- [../feature-template/frontend.md](./feature-template/frontend.md)
- [../feature-template/application.md](./feature-template/application.md)

**Template:**

1. **Actor:** 
   **System:** 
2. **Actor:** 
   **System:** 
3. **Actor:** 
   **System:** 

---

## Alternate Flow
Write only meaningful alternate paths.

Examples:
- barcode scan fails, user searches manually
- approval required before continuation
- payment method changed
- stock source changes

Do not write every tiny variation. Only document alternates that change the flow materially.

**Template:**

- Alternate flow A:
  - Actor:
  - System:
- Alternate flow B:
  - Actor:
  - System:

---

## Exception Flow
Write failures, rejections, or stop conditions.

Write here:
- what blocks completion
- what the user sees
- what the system preserves, reverses, or rejects

Do not write internal stack traces or low-level exception implementation.
Link those details instead:
- [../../07-backend/exception-handling-rules.md](../../07-backend/exception-handling-rules.md)
- [../../05-api/error-contract.md](../../05-api/error-contract.md)

**Template:**

- Exception:
  - Cause:
  - User-visible result:
  - System result:

---

## Permissions / Approvals
Write only the flow-specific access or approval impact.

Write here:
- whether the actor needs the feature enabled
- whether approval is required
- whether outlet-scope or tenant-scope access matters

Do not rewrite the full access model.
Link to the owning docs instead:
- [../../02-architecture/role-permission-capability-model.md](../../02-architecture/role-permission-capability-model.md)
- [../../16-templates/feature-template/permissions.md](../../16-templates/feature-template/permissions.md)

**Template:**

Required access:

Approval points:

Notes on default role vs effective assigned access:

---

## Outcome
Write the end result of the flow.

Write here:
- business result
- user-visible result
- important system/data result

Do not write full data-model or API details.
Link if needed:
- [../../04-data/database-overview.md](../../04-data/database-overview.md)
- [../../16-templates/feature-template/data-model.md](../../16-templates/feature-template/data-model.md)

**Template:**

Business outcome:

User-visible outcome:

System/data outcome:

---

## Related Files
Link only the documents needed to understand or maintain this flow.
Do not dump unrelated links.

**Template:**

- Module / feature:
- Business rules:
- API:
- Backend:
- Frontend:
- Data:
- Permissions:
