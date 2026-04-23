<!--
meta:
  title: Inventory / Stock Transfers / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [inventory, stock-transfers, api]
-->
> Hub: [[10-modules/inventory/features/stock-transfers/overview]]

# Stock Transfers - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Stock Transfers**.

## Endpoints / contract areas
- POST /inventory/transfers
- POST /inventory/transfers/{transferId}/approve
- POST /inventory/transfers/{transferId}/receive

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/inventory/features/stock-transfers/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/tenant-management/features/outlets/overview|Outlets]]
- [[10-modules/inventory/features/stock-ledger/overview|Stock Ledger]]

## Recommended reading order
Read after [[10-modules/inventory/features/stock-transfers/overview]], [[business-rules]], [[data-model]], and [[application]].
