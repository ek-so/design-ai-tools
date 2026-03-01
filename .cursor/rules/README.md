# Rules glossary

## What are rules?

Rules are persistent AI guidelines that shape how the model behaves across every conversation. Unlike commands (invoked explicitly) or skills (referenced by commands), rules apply automatically — no action needed.

## How they work

- Each rule is a `.mdc` file in `.cursor/rules/`
- Rules with `alwaysApply: true` are active in every conversation
- Rules can also be scoped to specific files or conditions via frontmatter
- Keep rules short — they consume context in every message

## All rules

| Rule | Scope | Description |
|------|-------|-------------|
| `general` | Always | Be direct, push back on assumptions, cite sources. |

## Configuration fields

| Field | Required | Description |
|-------|----------|-------------|
| `description` | Yes | One-line summary — helps Cursor decide when to apply scoped rules. |
| `alwaysApply` | No | `true` applies to every conversation. `false` or omitted means conditional. |
| `globs` | No | File patterns to scope the rule to (e.g. `**/*.ts`). |

## Creating a new rule

Add a `.mdc` file to `.cursor/rules/` with YAML frontmatter:

```markdown
---
description: One-line description of the rule
alwaysApply: true
---

- Rule instruction one
- Rule instruction two
```

Best practices:
- One concern per rule — don't mix tone with architecture with formatting
- Keep it under 5-7 bullet points
- Be specific and actionable — "no console.log in production" beats "write clean code"
- Use `alwaysApply: true` sparingly — every always-on rule costs context in every message
