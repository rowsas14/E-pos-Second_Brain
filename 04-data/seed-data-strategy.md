<!--
meta:
  title: Seed Data Strategy
  owner: Engineering / Data
  status: active
  last_reviewed: 2026-04-22
  tags: [seed-data, reference-data, initialization, multitenant]
-->

# Seed Data Strategy

## Purpose

This file explains what kinds of data should be seeded for this project and what must remain tenant-created.

The revised schema includes both stable reference sets and tenant-owned business/configuration data. Those two categories must not be mixed.

## Seed categories

| Category | Meaning | Typical owner |
|---|---|---|
| reference data | stable value sets used across the platform | engineering / migration layer |
| system-managed data | controlled data needed for platform operation | engineering or platform administration |
| tenant-created data | business data owned by the customer tenant | tenant admin or tenant operations |

## 1. Reference data suitable for global seeding

These are stable value sets already modeled as reference tables in the schema.

### Outlet and logistics references

- `outlet_types`
- `delivery_option_types`

### Inventory references

- `stock_movement_types`

### Discount references

- `discount_types`
- `discount_scopes`

### Payment references

- `payment_method_types`
- `payment_statuses`

### OTP references

- `otp_channels`
- `otp_purposes`

### Return / policy references

- `return_policy_types`

These are good candidates for migration-time seed data because they represent stable platform-wide vocabularies.

## 2. System-managed data that may need controlled initialization

### Permissions

`permissions` is system-managed in the schema and should be initialized carefully because it influences role assignment and sensitive-action control.

Permission definitions are not tenant business data. They are platform-owned capability definitions.

### Base role data

Roles themselves are tenant-owned in the revised schema. That means roles are not ideal global seed data in the same way as payment statuses or outlet types.

If the implementation needs starter roles during onboarding, that should be handled through controlled platform or onboarding flows rather than broad global seeding.

See:
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)

## 3. Data that should not be globally seeded

The following should remain tenant-created or tenant-onboarded:

- tenants
- outlets
- outlet addresses
- tenant staff users
- customers
- customer memberships
- brands
- suppliers
- categories
- products
- variants
- product images
- price lists
- tenant settings
- UI themes
- feature-flag configurations
- tenant tax classes
- membership tiers

These belong to the business identity and operating choices of a tenant.

## 4. Borderline cases that need intention

### Tax rates

`tax_rates` is tenant-owned in the schema.

Even if many tenants use similar tax patterns, this data should not be assumed globally safe. Seed it only if the product intentionally provides tenant-specific defaults during controlled onboarding.

### Membership tiers

Membership tiers are tenant-owned and business-specific. They should not be globally seeded as if every tenant shares the same loyalty model.

### UI themes and tenant settings

The schema supports tenant-owned theming and configuration. These can be initialized by onboarding flows, but they are not global reference seeds.

## 5. Seed discipline by type

| Data type | Where to initialize |
|---|---|
| stable reference tables | migrations |
| permission master data | controlled system initialization |
| tenant starter data | onboarding or tenant setup process |
| transactional data | never seed as static initialization |

## 6. Why this matters in this project

This platform is customer-specific per tenant. If tenant-owned data is seeded globally without discipline:

- isolation becomes unclear
- onboarding becomes inconsistent
- platform assumptions leak into tenant business control
- feature and configuration ownership becomes harder to reason about

## 7. Practical rules

1. seed platform-wide reference sets in migrations
2. initialize system-managed capability data intentionally
3. create tenant-owned data through tenant onboarding or tenant administration flows
4. do not hide tenant business assumptions inside migration seeds
5. keep seeded reference codes stable because operational rows depend on them

## Related documents

- [enum-and-reference-data-policy.md](./enum-and-reference-data-policy.md)
- [migration-strategy.md](./migration-strategy.md)
- [database-overview.md](./database-overview.md)
- [../02-architecture/role-permission-capability-model.md](../02-architecture/role-permission-capability-model.md)
- [../08-modules/platform-administration/features/tenant-onboarding/overview.md](../08-modules/platform-administration/features/tenant-onboarding/overview.md)
