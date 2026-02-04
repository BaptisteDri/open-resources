# open-resources

A curated, community-driven list of developer resources. Whether you're learning, building, or shipping.

Find tools, docs, and references in one place.

## How resources are organized

Resources live in **[resources.md](./resources.md)** and are grouped by precise category:

- **React frameworks** — Next.js, Expo
- **Headless components** — unstyled primitives (e.g. Base UI)
- **Designed components** — copy-paste UI (e.g. shadcn/ui)
- **Icons** — icon sets
- **Accessibility** — checklists, color contrast
- **Design** — checklists, palettes, wireframes
- **Data fetching** — TanStack Query, etc.
- **Validation** — Zod, etc.
- **Documentation** — docs lookup
- **Hosting** — deployment (e.g. Vercel)
- **Agentic development** — Cursor skills, AI agents, agentic workflows, MCP
- **Learning** — refactoring, TypeScript, skills

Each entry uses a consistent format: **name**, short **description**, and **link**.

## How to contribute

We use a simple contribution workflow so the list stays consistent and easy to maintain.

### Via Merge Request

1. **Fork** this repository.
2. **Create a branch** (e.g. `add-resource-react-query`).
3. **Add your resource** using the add-resource skill for your agent. Do **not** edit `resources.md` by hand.
   - **Cursor**: [.cursor/skills/add-resource/SKILL.md](./.cursor/skills/add-resource/SKILL.md)
   - **Claude Code**: [.claude/skills/add-resource/SKILL.md](./.claude/skills/add-resource/SKILL.md)
4. **Commit and push** your branch.
5. **Open a Merge Request** with a short description of the resource and why it’s useful.

### Important

**Please do not edit `resources.md` manually.** Use the add-resource skill (Cursor or Claude Code) so that:

- Formatting stays consistent
- Entries are placed in the right section
- The list stays sorted and easy to scan

### Skills for multiple agents

The same add-resource skill is provided for **Cursor** (`.cursor/skills/add-resource/`) and **Claude Code** (`.claude/skills/add-resource/`). The instructions are identical; each agent uses its own folder convention.

To keep skills in sync across agents in other projects, you can use tools such as [Skills CLI](https://dhruvwill.github.io/skills-cli/) (single store, sync to Cursor/Claude/etc.) or [agent-rules-sync](https://pypi.org/project/agent-rules-sync/) (real-time sync). Here we maintain both copies in the repo so contributors can use either Cursor or Claude Code as-is.

We're happy to have you contribute. Thanks for helping grow this list.
