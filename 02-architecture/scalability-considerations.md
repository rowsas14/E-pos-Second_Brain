<!--
meta:
  title: Scalability Considerations
  owner: Architecture / Engineering
  status: active
  last_reviewed: 2026-04-22
  tags: [architecture, scalability, performance, multitenant, operations]
-->

# Scalability Considerations

## Purpose

This document explains the main scalability considerations for the Unified Commerce Platform based on the current project direction.

It stays at practical architecture level and does not invent unsupported infrastructure decisions.

## Why scalability matters in this project

The platform is expected to support:

- multiple tenants
- multiple outlets
- growing transaction volume
- shared commerce foundations for POS and E-Commerce
- tenant-owned configuration and reporting

The architecture therefore needs to scale without redesigning the core operating model.

## Main areas likely to feel scale pressure first

### 1. POS speed-sensitive operations

POS behavior is explicitly required to stay responsive and optimized for cashier speed.

The first pressure points are likely to be:

- product scan and search response time
- price resolution during checkout
- cart and payable total updates
- payment completion flow
- receipt generation and printing handoff

### 2. Inventory movement growth

Inventory follows a ledger + projection model.

That means scale pressure can appear in both:

- growing stock movement history
- keeping current balances accurate and fast to read

As transaction volume grows, the balance between authoritative movement history and fast operational stock reads becomes more important.

### 3. Payment and allocation workflows

Payments are used across:

- sales
- orders
- refunds
- exchange differences

Pressure is likely in:

- payment recording
- status updates
- allocation correctness
- refund tracking
- reconciliation-sensitive POS contexts

These areas cannot sacrifice correctness for speed.

### 4. Reporting growth

Reporting requirements already include outlet-wise and channel-wise visibility with sales, returns, payments, discounts, and tax perspectives.

As transaction volume grows, reporting is likely to create pressure on:

- aggregation cost
- report freshness expectations
- historical query size

### 5. Tenant and configuration growth

Because the platform is customer-specific per tenant, configuration growth matters.

Pressure can increase through:

- more tenants
- more outlets per tenant
- more feature flags and settings
- more theme or scope combinations
- more permission and capability combinations

## Multi-tenant growth considerations

Growth is not only more rows in tables. It is also more isolation-sensitive behavior.

As tenants and outlets grow, the architecture must continue to preserve:

- same-tenant validation
- correct permission scope resolution
- correct configuration scope resolution
- safe reporting visibility
- safe auditability of sensitive actions

## Channel-specific scaling pressure

### POS

POS pressure is mainly around speed and operational confidence.

Relevant concerns:

- cashier-facing response time
- fast product lookup
- stock and pricing correctness during sale execution
- payment flow reliability during business hours

### E-Commerce

E-Commerce pressure is mainly around:

- catalog reads
- cart and order activity
- reservation-sensitive inventory behavior
- order and fulfillment tracking growth

## Architecture implications

The current architecture direction already supports several helpful principles:

- modular architecture
- shared foundations with clear document separation
- inventory ledger plus balance projection
- transaction-sensitive handling for money and stock flows
- tenant-scoped configuration rather than customer-specific source-code branching

Those choices matter because they reduce the need to redesign core business ownership just because scale increases.

## What should be watched closely first

| Area | Why it matters early |
|---|---|
| POS product scan/search | directly affects cashier speed |
| price and total calculation | directly affects sale completion speed and accuracy |
| stock balance resolution | affects both POS and E-Commerce |
| stock movement posting | affects inventory correctness and auditability |
| payment status and allocation logic | affects money correctness |
| reporting queries | likely to grow faster than simple CRUD queries |
| feature/configuration lookup | grows with tenant customization |

## What this file does not decide

This file does not lock in specific infrastructure choices such as hosting topology, caching products, queues, or reporting pipeline design.

Those decisions should be made only when supported by approved implementation direction and recorded appropriately.

## Related documents

- [system-overview.md](./system-overview.md)
- [multi-tenant-architecture.md](./multi-tenant-architecture.md)
- [backend-architecture.md](./backend-architecture.md)
- [../04-data/database-overview.md](../04-data/database-overview.md)
- [../04-data/migration-strategy.md](../04-data/migration-strategy.md)
- [../07-backend/transaction-handling-rules.md](../07-backend/transaction-handling-rules.md)
- [../13-testing-quality/test-strategy.md](../13-testing-quality/test-strategy.md)
