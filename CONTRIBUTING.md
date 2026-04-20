# Contributing

Thanks for wanting to help. Here's how it works.

## Adding a service to HOMELAB

Open `skills/HOMELAB/skill.md` and find the `SERVICES CATALOG` section inside `ROUTE 2 — SERVICES`. Add your service under the appropriate category:

```
▸ Service Name   — one-line description of what it does
```

Include: what it does, system requirements, install path, and key config flags in the Learn route's concept list.

## Adding a new skill

1. Create `skills/YOUR-SKILL/skill.md` following the frontmatter format:

```markdown
---
name: SKILL-NAME
description: Short description. Triggers on "keyword", "keyword".
tools: Bash, Write, Read
model: claude-sonnet-4-6
---

Skill prompt content here.
```

2. Add a row to the Skills table in `README.md`
3. Create `skills/YOUR-SKILL/README.md` with install + usage docs
4. Open a PR

## Standards

- Skills should be interactive — menu-driven, ask before destructive actions
- Always include an Obsidian save route if the skill generates persistent output
- Bash commands must be safe by default — no `rm -rf` without explicit confirmation
- Keep recommendations opinionated — vague advice is useless
- Test your skill in Claude Code before opening a PR

## PR format

Title: `feat(skill-name): what you added`

Body: what the skill does, what routes/commands changed, how you tested it.
