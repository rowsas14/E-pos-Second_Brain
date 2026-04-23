<!--
meta:
  title: Sales POS / Tills & Sessions / Validations
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [sales-pos, tills-sessions, validations]
-->
> Hub: [[10-modules/sales-pos/features/tills-sessions/overview]]

# Tills & Sessions - Validations

## Purpose
This file records input, business, and **workflow** validations for **Tills & Sessions**.

## Validation rules
- block new open session if till already open
- validate till belongs to selected outlet and tenant

## Validation dependency map
- [[business-rules]] defines the rule intent.
- [[data-model]] defines structural constraints.
- [[application]] decides when validation runs.
- [[api]] exposes validation failures to clients.

## Related features
- [[10-modules/sales-pos/features/cash-movements/overview|Cash Movements]]
- [[10-modules/sales-pos/features/pos-checkout/overview|POS Checkout]]

## Recommended reading order
Read after [[business-rules]] and [[data-model]], then before [[api]] and [[backend]].
