<!--
meta:
  title: Documentation Rules
  owner: Engineering / Documentation
  status: active
  last_reviewed: 2026-04-22
  tags: [documentation-rules, source-of-truth, markdown-standards, governance]
-->

# Documentation Rules

## Purpose

These rules keep the 2nd Brain reliable during real project work.

This project already has an approved business direction, schema direction, architecture direction, and cleaned folder structure. Documentation must support those approved decisions instead of competing with them.

## Source-of-truth priority

When writing or updating markdown files, use this order:

1. approved uploaded project documents
2. approved cleaned 2nd Brain structure
3. approved ADRs in [../03-decisions/](../03-decisions/)
4. established project rules already captured in this documentation system
5. implementation-facing docs that refine the above without contradicting them

If two sources conflict, do not silently blend them. Resolve the difference in the owning document or record the change through an ADR.

## Project grounding rules

Do not write generic software documentation.

Every document must stay grounded in this project’s actual model:

- unified commerce platform with **E-POS + E-Commerce**
- multi-tenant operating model
- separate platform admin and tenant staff accounts
- tenant-bound staff users
- tenant-specific customers and memberships
- variant-level sellable flows
- ledger + projection inventory model
- returns and exchanges as separate business documents
- touchscreen-first, barcode-first, low-typing POS behavior
- customer-specific tenant configuration
- platform-controlled feature assignment with tenant-side configuration
- implementation stack: **.NET Web API + Clean Architecture**, **PostgreSQL + EF Core**, **React + TypeScript + Tailwind CSS**

If a statement is not supported by approved source material or the current project structure, do not guess.

## Metadata rules

Every markdown file must start with metadata.

```html
<!--
meta:
  title: Document Title
  owner: Responsible Team or Role
  status: active
  last_reviewed: YYYY-MM-DD
  tags: [tag-one, tag-two]
-->
```

### Metadata expectations

| Field | Rule |
|---|---|
| `title` | match the real purpose of the file |
| `owner` | show who is responsible for keeping the file accurate |
| `status` | use a real document state such as `active`, `draft`, or `archived` |
| `last_reviewed` | update when content changes, not just because the file was opened |
| `tags` | support search and discovery without repeating the whole path |

## Writing quality rules

### Write the content that belongs to the file

Examples:

- `01-product/` is for business intent, not backend rules
- `04-data/` is for schema and data-governance rules, not screen layout notes
- `05-api/` is for platform-wide API standards, not one feature’s business justification
- `08-modules/<module>/features/<feature>/business-rules.md` is for that feature’s business rules, not global architecture theory

### Keep files practical

Use short sections, readable tables, and small diagrams only when they improve understanding.

Write so the file can be used during active implementation, review, QA, or debugging.

### Keep files focused

Prefer around **180 lines or less** where practical.

A file may exceed that when the subject genuinely needs it, but do not add bulk to make a document look more complete than it is.

### Use internal links

Link directly to the next correct document when the reader needs more detail.

### Avoid filler and duplication

Do not add:

- fake citations or system reference tokens
- broken placeholders
- repeated paragraphs copied into many folders
- generic best-practice text that is not tied to this platform
- unsupported claims about workflows, architecture, or feature behavior

## When to update an existing file vs create a new file

### Update an existing file when

- the topic already belongs to an existing document
- you are refining, correcting, or extending a documented rule
- the change affects the current owner file without creating a new distinct subject

### Create a new file when

- the topic is genuinely separate and would make the existing file confusing or oversized
- the current folder pattern already expects that file type
- the subject needs its own ownership and update history

### Do not create a new file when

- the reason is only convenience
- the content would duplicate an existing rule in another folder
- the topic belongs in the current file with a new section

## File naming rules

- keep file names lowercase and hyphen-separated where the structure already follows that pattern
- use stable names that describe the document purpose, not temporary tasks
- do not rename files casually because links across the vault depend on them
- when a legacy name already exists and is accepted by the project structure, keep it unless the change is intentional and coordinated

## Section structure rules

A good file usually contains:

1. purpose
2. scope or ownership
3. the actual project-specific rules or guidance
4. related links

Not every file needs the same headings, but the structure should help a reader move from context to action.

## Linking rules

- use relative internal `.md` links
- link to the owning file instead of duplicating its content
- add links where a reader must continue to another document to complete the task
- avoid link dumping; only link to the next useful documents

## Separation rules by folder type

| Folder area | What it should own |
|---|---|
| `00-start-here/` | navigation, documentation rules, reading order |
| `01-product/` | business intent, goals, scope |
| `02-architecture/` | system boundaries, operating models, capability model |
| `03-decisions/` | ADRs and important recorded design decisions |
| `04-data/` | schema rules, naming, migration, tenant consistency |
| `05-api/` | API-wide standards |
| `06-frontend/` | frontend-wide standards and POS UI guidance |
| `07-backend/` | backend-wide implementation rules |
| `08-modules/` | module and feature documentation |
| `11-16` | cross-cutting configuration, security, testing, operations, AI rules, templates |
| `19-project-history/` | project-wide history and major changes |

## Alignment with real implementation

Documentation must not drift away from implementation.

After meaningful changes in code, schema, API, permissions, workflows, or configuration:

- update the owning markdown file
- update `last_reviewed`
- update feature `changelog.md` when the change materially affects feature behavior or documentation
- update project-wide history files when the impact is broader than one feature
- record a new ADR when the change affects system boundaries or major design direction

## Ownership rules for repeated topics

Do not repeat the same rule in many folders without a clear reason.

Use this pattern:

- the owning document defines the rule
- related documents summarize only what is necessary for local context
- related documents link back to the owner file

## Related documents

- [README.md](./README.md)
- [folder-structure-guide.md](./folder-structure-guide.md)
- [how-to-use-this-brain.md](./how-to-use-this-brain.md)
- [../03-decisions/ADR-index.md](../03-decisions/ADR-index.md)
- [../16-templates/README.md](../16-templates/README.md)
