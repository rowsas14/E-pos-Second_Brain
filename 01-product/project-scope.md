<!--
meta:
  title: Project Scope
  owner: Product / Business Analysis
  status: active
  last_reviewed: 2026-04-23
  tags: [product, scope, in-scope, out-of-scope, unified-commerce]
-->

# Project Scope

## Purpose

This document defines the current project boundaries for the Unified Commerce Platform.

It should be used to decide whether a requested feature area, document change, implementation task, or QA expectation belongs to the current project direction.

For the business problem, see [business-goal.md](./business-goal.md). For the intended business outcomes, see [business-objectives.md](./business-objectives.md).

## Scope summary

The project covers a **multi-tenant unified commerce platform** with shared foundations for **E-POS** and **E-Commerce**.

The scope includes:

- platform and tenant administration
- tenant-bound staff identity and access
- catalog and variant-based sellable data
- inventory and stock control
- POS operations
- E-Commerce operations
- payments, discounts, returns, and exchanges
- reporting and auditability
- tenant-scoped settings, themes, and configuration

The scope specifically prioritizes a **touchscreen-first, cashier-friendly POS operating model** rather than a generic desktop billing screen.

## In-scope areas

### 1. Platform and tenant management

This includes:

- tenant onboarding by platform-side administration
- tenant activation and suspension
- base tenant configuration
- outlet creation and maintenance
- channel activation for POS, E-Commerce, or hybrid usage
- tenant-specific themes and scoped settings
- platform-controlled feature availability assignment with tenant-side configuration

A feature may have a default role mapping during onboarding or initial setup, but final access is still platform-controlled and tenant-configured at runtime.

Related reading:

- [../08-modules/platform-administration/README.md](../08-modules/platform-administration/README.md)
- [../08-modules/tenant-management/README.md](../08-modules/tenant-management/README.md)
- [../11-config-and-customization/README.md](../11-config-and-customization/README.md)

### 2. Staff identity and access

This includes:

- tenant-bound staff users
- tenant-level and outlet-level roles
- permission control for operational areas such as cashier, manager, inventory, and E-Commerce staff
- separation of platform admin from tenant staff accounts
- flexible feature-to-role assignment and tenant-side usage configuration

Default role mappings may exist as starter assignments, but they do not replace platform-admin capability assignment or tenant-side configuration.

Related reading:

- [../08-modules/identity-access/README.md](../08-modules/identity-access/README.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)

### 3. Product and catalog management

This includes:

- categories
- brands
- suppliers
- products
- variants
- attributes
- SKU and barcode support
- channel availability rules
- product imagery for online use
- return-policy classification at product level

Related reading:

- [../08-modules/catalog/README.md](../08-modules/catalog/README.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)

### 4. Inventory and stock management

This includes:

- inventory balances by outlet and variant
- stock movement ledger
- reservation handling for online orders
- stock transfers
- stocktakes
- adjustment, damage, and return-related inventory handling

Related reading:

- [../08-modules/inventory/README.md](../08-modules/inventory/README.md)
- [../04-data/tenant-consistency-rules.md](../04-data/tenant-consistency-rules.md)

### 5. POS operations

This includes:

- till and session management
- barcode scan and quick-add billing flows
- hold and recall sale
- cash, card, QR, and split payment support
- receipt printing
- returns and exchanges support
- visible totals during checkout
- low-typing cashier workflows
- touchscreen-first retail execution

Related reading:

- [../08-modules/sales-pos/README.md](../08-modules/sales-pos/README.md)
- [../06-frontend/pos-ui-principles.md](../06-frontend/pos-ui-principles.md)

### 6. E-Commerce operations

This includes:

- product listing and search
- product detail presentation
- cart and checkout flows
- guest cart and guest checkout readiness
- customer login and account handling
- order status tracking
- fulfillment and delivery readiness

Related reading:

- [../08-modules/orders-ecommerce/README.md](../08-modules/orders-ecommerce/README.md)
- [../08-modules/fulfillment-logistics/README.md](../08-modules/fulfillment-logistics/README.md)

### 7. Payments, discounts, returns, and exchanges

This includes:

- payment capture and allocation
- discount requests and approvals
- direct discount application tracking
- coupon support
- return documents linked to original sales or orders
- exchange documents
- refund allocation
- exchange difference collection or refund handling

Related reading:

- [../08-modules/payments/README.md](../08-modules/payments/README.md)
- [../08-modules/discounts-promotions/README.md](../08-modules/discounts-promotions/README.md)
- [../08-modules/returns-exchanges/README.md](../08-modules/returns-exchanges/README.md)

### 8. Reporting and audit

This includes:

- daily sales reporting
- channel and outlet reporting
- payment summaries
- return summaries
- discount visibility
- auditability of sensitive actions and business events

Related reading:

- [../08-modules/reporting/README.md](../08-modules/reporting/README.md)
- [../12-security-and-compliance/audit-requirements.md](../12-security-and-compliance/audit-requirements.md)

## Out-of-scope areas at this stage

The following are outside current scope unless separately approved or explicitly expanded later.

### 1. Full accounting or general ledger

The platform does not currently include full accounting coverage or a complete general ledger function.

### 2. Payroll and HR management

Employee payroll, HR workflows, and general workforce administration are not part of this scope.

### 3. Full ERP procurement process in the MVP

The platform may include supplier and stock-related structures, but it does not currently scope a full ERP procurement lifecycle for the MVP.

### 4. Advanced CRM automation

The current direction does not include a full advanced CRM automation engine.

### 5. Marketplace integrations in the initial release

Marketplace integrations are outside the initial release boundary.

### 6. Advanced loyalty engine beyond the current foundation

The current scope supports tenant-specific membership foundations, but not a broader advanced loyalty engine beyond that foundation.

### 7. Native mobile apps unless separately approved

The initial project direction does not include native mobile applications unless separately approved.

## Scope control notes

### A request is likely in scope when

- it strengthens the shared POS + E-Commerce operating model
- it fits the tenant-specific unified commerce direction
- it supports catalog, inventory, sales, orders, payments, returns, reporting, or tenant configuration
- it supports the approved operating model for staff, customers, permissions, or outlets

### A request needs extra review when

- it treats a default role mapping as if it were a permanent entitlement
- it expands tenant capability assignment beyond platform governance
- it changes core operating boundaries between platform control and tenant control

## Related documents

- [README.md](./README.md)
- [business-goal.md](./business-goal.md)
- [business-objectives.md](./business-objectives.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
