<!--
meta:
  title: Customers / Customer Auth / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [customers, customer-auth, business-rules]
-->
> Hub: [[10-modules/customers/features/customer-auth/overview]]

# Customer Auth - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Customer Auth** feature inside the **Customers** module.

## Core rules
- one auth account per customer per tenant
- identity provider combinations must be unique within tenant when provider_subject exists
- supported providers include local, google, apple, and otp

## Why these rules matter
Online customers need account access, but auth identities must remain tenant-aware so one provider/email can exist per tenant separately.

## Related feature files
- [[10-modules/customers/features/customer-auth/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/customers/features/customer-profiles/overview|Customer Profiles]]
- [[10-modules/customers/features/customer-addresses/overview|Customer Addresses]]
- [[10-modules/memberships/features/customer-memberships/overview|Customer Memberships]]

## Recommended reading order
Read after [[10-modules/customers/features/customer-auth/overview]], then before [[application]], [[api]], and [[validations]].
