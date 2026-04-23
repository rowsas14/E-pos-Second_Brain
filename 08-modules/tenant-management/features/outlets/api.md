<!--
meta:
  title: Tenant Management / Outlets / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [tenant-management, outlets, api]
-->
> Hub: [[10-modules/tenant-management/features/outlets/overview]]

# Outlets - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Outlets**.

## Endpoints / contract areas
- POST /outlets
- GET /outlets
- PATCH /outlets/{outletId}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/tenant-management/features/outlets/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]
- [[10-modules/sales-pos/features/tills-sessions/overview|Tills & Sessions]]
- [[10-modules/fulfillment-logistics/features/fulfillment-assignment/overview|Fulfillment Assignment]]

## Recommended reading order
Read after [[10-modules/tenant-management/features/outlets/overview]], [[business-rules]], [[data-model]], and [[application]].
