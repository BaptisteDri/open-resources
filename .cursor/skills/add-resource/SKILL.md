---
name: add-resource
description: Adds a developer resource to resources.md in the correct section, sorted alphabetically. Use when the user wants to add a resource, contribute to the list, or insert a new entry (name, description, URL, category).
---

# Add resource to open-resources

## Goal

Add a single developer resource to `resources.md` so the list stays consistent: correct section, alphabetical order, and unchanged markdown structure.

## Inputs

The user (or the contribution workflow) must provide:

| Input | Required | Description |
|-------|----------|-------------|
| **Resource name** | Yes | Display name of the resource (e.g. "React", "Docker"). |
| **Description** | Yes | One short sentence describing what it is or what it’s for. |
| **URL** | Yes | Valid link (https preferred). |
| **Category** | Yes | One of: `React frameworks`, `Headless components`, `Designed components`, `Icons`, `Accessibility`, `Design`, `Data fetching`, `Validation`, `Documentation`, `Hosting`, `Agentic development`, `Learning`. Case-sensitive. |

If any required input is missing, ask the user before changing `resources.md`.

## Responsibilities

1. **Read** the current `resources.md` from the repository root.
2. **Resolve the section** using the given category (e.g. `Icons` → section `## Icons`).
3. **Create the section** if it does not exist: add `## CategoryName` and a table with headers `| Resource | Description | Link |`, then add the new row.
4. **Insert the new row** in the correct section. Row format: `| {Resource name} | {Description} | {URL} |`.
5. **Sort rows** within that section alphabetically by **Resource** (first column). Header row stays first; do not sort the header into the list.
6. **Preserve** all other content and markdown (intro, Table of contents, other sections, blank lines, link format).
7. **Write** the updated content back to `resources.md` only; do not create or modify other files unless the user explicitly asks.

## Rules and constraints

- **One resource per invocation**: Add only the single resource specified by the user.
- **No duplicates**: If a resource with the same name and same section already exists, do not add it again; inform the user.
- **Category exact match**: Use the category name exactly as in the list (React frameworks, Headless components, Designed components, Icons, Accessibility, Design, Data fetching, Validation, Documentation, Hosting, Agentic development, Learning). If the user gives a new category name, create a new section with that exact title, add it in logical order (after existing sections), and add a new line to the Table of contents: `- [CategoryName](#category-name)` (anchor = heading in lowercase with spaces as hyphens).
- **Sorting**: Alphabetical order is case-insensitive by resource name (first column). Use the same table format as existing rows.
- **Links**: Keep URLs as-is; do not transform or shorten them.
- **Description**: Use the user’s description as given; keep it to one short sentence.
- **Determinism**: Same inputs must always produce the same result: same section, same row format, same alphabetical position.

## Entry format

Each resource is a single table row:

```markdown
| Resource name | Short description. | https://example.com |
```

- No leading/trailing pipes outside the table.
- Table header in existing sections is: `| Resource | Description | Link |`.
- New sections use the same header.

## Workflow summary

1. Read `resources.md`.
2. Parse inputs (name, description, URL, category).
3. Find or create the section for the category.
4. If duplicate (same name in same section): stop and inform the user.
5. Insert the new row and sort all data rows in that section by Resource name (A–Z).
6. If a new section was added, add its entry to the Table of contents (after the intro, before the first `---`).
7. Write the full file back to `resources.md`.

Keep the logic simple: one pass to read, one pass to update, one write. No extra automation or scripts unless the user requests them.
