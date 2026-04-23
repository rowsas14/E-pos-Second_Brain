<!--
meta:
  title: Feature Template - Bugs
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, bugs, issue-tracking]
-->

# Feature Bugs Template

## Purpose of this file

Use this file to record **feature-specific bugs**.

This file should help the team understand recurring or important issues in the feature and keep bug knowledge close to the feature documentation.

## What belongs here

Record bugs that are specific enough to this feature that future work on the feature should see them.

Include:

- bug title
- status
- date found
- affected area
- symptom summary
- root cause summary
- fix summary
- related docs or code areas

## What should not be placed here

Do not use this file as a full issue tracker replacement for every tiny defect.

Use project-wide history files when the bug affects multiple modules or becomes a major incident:

- [../../../../19-project-history/overall-bugs.md](../../../../19-project-history/overall-bugs.md)
- [../../../../19-project-history/major-incidents.md](../../../../19-project-history/major-incidents.md)

## Status guidance

Use clear statuses such as:

- `open`
- `in-progress`
- `fixed`
- `blocked`
- `deferred`

## Recommended structure

## Bug entries

| Bug title | Status | Date found | Affected area | Root cause summary | Fix summary |
|---|---|---|---|---|---|
| `[Bug title]` | `[status]` | `YYYY-MM-DD` | `[area]` | `[summary]` | `[summary]` |

## Detailed bug records (optional)

### `[Bug title]`

- **Status:** `[open / in-progress / fixed / blocked / deferred]`
- **Date found:** `YYYY-MM-DD`
- **Affected area:** `[API / backend / frontend / workflow / data / permission]`
- **Symptom summary:** `[What was observed]`
- **Root cause summary:** `[Why it happened]`
- **Fix summary:** `[What changed]`
- **Related files:** `[Links]`
- **Related tests / validations:** `[Links]`

## Related files

- [edge-cases.md](./edge-cases.md)
- [changelog.md](./changelog.md)
- [../../../../13-testing-quality/bug-handling-rules.md](../../../../13-testing-quality/bug-handling-rules.md)
- [../../../../15-ai-ide-rules/bug-fix-rules.md](../../../../15-ai-ide-rules/bug-fix-rules.md)

## Final check before saving

Confirm that this file:

- records bugs that matter for future feature work
- captures root cause and fix summary, not just symptom
- links to related files or tests when useful
- stays aligned with project-wide bug history when impact is broader
