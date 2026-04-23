<!--
meta:
  title: Fulfillment & Logistics / Fulfillment Assignment / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [fulfillment-logistics, fulfillment-assignment, api]
-->
> Hub: [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]

# Fulfillment Assignment - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Fulfillment Assignment**.

## Endpoints / contract areas
- PATCH /orders/{orderId}/fulfillment-outlet
- GET /orders/{orderId}/fulfillment-options

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/reservations/overview|Reservations]]
- [[10-modules/fulfillment-logistics/features/deliveries/overview|Deliveries]]

## Recommended reading order
Read after [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview]], [[business-rules]], [[data-model]], and [[application]].
