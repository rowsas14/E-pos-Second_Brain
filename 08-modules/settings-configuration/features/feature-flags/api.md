<!--
meta:
  title: Settings & Configuration / Feature Flags / Api
  owner: Commerce Engineering
  status: active
  last_reviewed: 2026-04-17
  tags: [settings-configuration, feature-flags, api]
-->
> Hub: [[10-modules/settings-configuration/features/feature-flags/overview]]

# Feature Flags - API

## Purpose
This file lists the likely **API** surface and contract concerns for **Feature Flags**.

## Endpoints / contract areas
- GET /feature-flags
- PUT /feature-flags/{flagKey}
- GET /feature-flags/resolve/{flagKey}

## API concerns
- Enforce **tenant** context and role checks.
- Keep request/response contracts aligned with [[data-model]] and [[business-rules]].
- Apply **idempotency** where repeated submit can create duplicate business effects.
- Return errors using the project-wide **error contract** rules.

## Related feature files
- [[10-modules/settings-configuration/features/feature-flags/overview]]
- [[application]]
- [[permissions]]
- [[validations]]
- [[frontend]]

## Related features
- [[10-modules/settings-configuration/features/tenant-settings/overview|Tenant Settings]]
- [[10-modules/settings-configuration/features/ui-themes/overview|UI Themes]]

## Recommended reading order
Read after [[10-modules/settings-configuration/features/feature-flags/overview]], [[business-rules]], [[data-model]], and [[application]].
