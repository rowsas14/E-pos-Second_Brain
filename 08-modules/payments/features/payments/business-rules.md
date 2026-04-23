<!--
meta:
  title: Payments / Payments / Business Rules
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [payments, payments, business-rules]
-->
> Hub: [[10-modules/payments/features/payments/overview]]

# Payments - Business Rules

## Purpose
This file captures the business restrictions and commercial intent for the **Payments** feature inside the **Payments** module.

## Core rules
- payment_direction is inbound or outbound
- payment_purpose is sale, order, refund, or exchange_difference
- refund payout is a separate outbound payment row

## Why these rules matter
The schema intentionally centralizes money movement instead of splitting every transaction type into unrelated models.

## Related feature files
- [[10-modules/payments/features/payments/overview]]
- [[data-model]]
- [[application]]
- [[permissions]]
- [[validations]]

## Related features
- [[10-modules/payments/features/payment-allocations/overview|Payment Allocations]]
- [[10-modules/payments/features/refunds/overview|Refunds]]
- [[10-modules/payments/features/provider-transactions/overview|Provider Transactions]]

## Recommended reading order
Read after [[10-modules/payments/features/payments/overview]], then before [[application]], [[api]], and [[validations]].
