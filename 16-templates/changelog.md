<!--
meta:
  title: Feature Template - Changelog
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [template, feature-docs, changelog, history]
-->

# Feature Changelog Template

## Purpose of this file

Use this file to record **feature-level change history**.

Keep this file focused on meaningful changes to the feature’s behavior, contracts, rules, implementation direction, or documentation.

This file should help someone answer:

- what changed
- when it changed
- who changed it
- what documents or areas were affected
- what impact the change had

## What belongs here

Include entries for:

- feature rule changes
- API changes
- permission changes
- data model changes
- workflow changes
- important backend or frontend changes
- documentation corrections that affect understanding or implementation

## What should not be logged here

Do not log tiny formatting edits or trivial wording changes unless they change meaning.

Broad project-wide changes that affect many areas should also be reflected in:

- [../../../../19-project-history/overall-changelog.md](../../../../19-project-history/overall-changelog.md)
- [../../../../19-project-history/breaking-changes.md](../../../../19-project-history/breaking-changes.md) when relevant

## Entry format rules

- newest entries first
- keep summaries factual and short
- link affected files when useful
- state impact clearly

## Recommended structure

## Change log entries

| Date | Changed by | Summary | Affected files | Impact |
|---|---|---|---|---|
| `YYYY-MM-DD` | `[Name / Team / Role]` | `[What changed]` | `[files]` | `[impact]` |

## Detailed entries (optional)

Use this section only when one change needs more explanation.

### `YYYY-MM-DD - [Short title]`

- **Changed by:** `[Name / Team / Role]`
- **Summary:** `[Summary]`
- **Affected files:** `[Links]`
- **Impact:** `[Impact]`
- **Related issue / ADR / bug:** `[Link if relevant]`

## Related files

- [overview.md](./overview.md)
- [bugs.md](./bugs.md)
- [../../../../19-project-history/overall-changelog.md](../../../../19-project-history/overall-changelog.md)

## Final check before saving

Confirm that this file:

- captures meaningful feature history
- is easy to scan
- makes impact visible
- stays synchronized with broader project history when necessary
