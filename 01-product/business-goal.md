<!--
meta:
  title: Business Goal
  owner: Product / Business Analysis
  status: active
  last_reviewed: 2026-04-22
  tags: [product, business-goal, problem-statement, unified-commerce]
-->

# Business Goal

## Purpose

This document explains the business problem the platform is solving, why that problem matters, and what business outcome the platform is meant to produce.

For target outcomes, see [business-objectives.md](./business-objectives.md). For current boundaries, see [project-scope.md](./project-scope.md).

## The business problem

Many retail businesses operate physical billing and online selling through disconnected systems.

That causes the same business to manage commerce in separate places instead of one shared operating model.

In this project, the problem is not described as a general “digital transformation” issue. It is a concrete operational problem across retail channels.

## Current pain in disconnected systems

When POS and E-Commerce are disconnected, businesses face repeated operational problems:

- product maintenance is duplicated
- stock visibility becomes unreliable across channels
- pricing can become inconsistent between store and online contexts
- customer history becomes fragmented
- order and payment handling become harder to trace
- returns and exchanges become harder to manage cleanly
- reporting becomes weaker because the business is looking at split data sets
- staff effort increases because teams compensate manually for system gaps

These pains are especially important in businesses that need both front-counter billing speed and online order handling.

## Why this matters for this project

This platform is being defined as a **multi-tenant unified commerce platform**. That means the goal is not only to add online selling beside a POS. The goal is to create one product foundation that can support:

- shared catalog and variant structures
- shared pricing foundations
- channel-aware stock handling
- tenant-specific customer relationships
- payment capture and allocation
- returns and exchanges as explicit business records
- tenant-scoped reporting and configuration

The business need is therefore broader than “make POS and website talk to each other.” The real need is to reduce operational fragmentation while preserving clean tenant boundaries and customer-specific configuration.

## Business need

The business needs a platform that can:

1. unify core commerce operations across store and online channels
2. keep each tenant operationally isolated
3. support tenant-specific business control without breaking platform governance
4. enable fast retail billing for in-store staff
5. provide clearer operational visibility across products, stock, orders, payments, discounts, and returns

## Problem vs intended outcome

| Current problem | Intended business outcome |
|---|---|
| separate systems for store and online | one shared commerce foundation |
| duplicated maintenance effort | one place to manage key commerce data |
| stock mismatch and weak visibility | stronger cross-channel stock control |
| inconsistent pricing and promotions | more consistent commercial behavior |
| fragmented customer history | tenant-specific customer handling in one platform context |
| weak reporting | clearer tenant, outlet, channel, payment, and return visibility |
| slow or awkward retail workflows | cashier-friendly POS operation |
| hard-coded feature behavior | flexible feature assignment and tenant-side configuration |

## Why this platform exists

This platform exists to solve the business cost of disconnected retail operations while preserving the control model required for a multi-tenant product.

That means the platform must do two things at the same time:

- unify commerce operations where the business benefits from shared foundations
- enforce separation where tenant boundaries, user boundaries, and customer boundaries must remain explicit

This is why the product model includes all of the following together:

- separate platform admin and tenant staff models
- tenant-bound staff users
- tenant-specific customers and memberships
- variant-level sellable operations
- explicit returns and exchange documents
- tenant-side configuration within platform-governed feature access

## Target business outcome

The intended business outcome is a commerce platform where each tenant can run physical and online selling through one structured system with:

- clearer control over products, pricing, stock, and configuration
- faster and more reliable POS execution
- cleaner online order handling
- better reporting visibility
- less operational duplication
- cleaner governance of access and capability usage

## What this file does not define

This file does not define detailed scope, implementation rules, or technical behavior.

For those, continue with:

- [business-objectives.md](./business-objectives.md)
- [project-scope.md](./project-scope.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)

## Related documents

- [README.md](./README.md)
- [business-objectives.md](./business-objectives.md)
- [project-scope.md](./project-scope.md)
- [../02-architecture/system-overview.md](../02-architecture/system-overview.md)
- [../02-architecture/multi-tenancy-model.md](../02-architecture/multi-tenancy-model.md)
