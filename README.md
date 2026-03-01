<p align="center">
  <img src="assets/cover.png" alt="design-ai-tools cover" width="100%" />
</p>

# design-ai-fuel

A ready-made `.cursor/` setup for product designers and product people who build with Cursor. Commands, rules, and skills — clone the repo, copy the folder, start using.

## What's inside

### Commands (`.cursor/commands/`)

Reusable AI workflows you invoke with `/command-name` in Cursor's chat. See the [full glossary](.cursor/commands/README.md).

Commands are designed as a **pipeline** — each step feeds into the next, taking you from idea to shipped, reviewed code:

```
/explore → /one-pager → /critique → /code-explore → /code-plan → /code-execute → /code-review → /code-review-peer → /document
```

Every predecessor is optional input, so each command also works standalone. The only hard dependency is `/code-execute`, which requires a plan from `/code-plan`.

### Agents (`.cursor/agents/`)

Specialized subagents that run in parallel or get auto-delegated by the parent agent. See the [full glossary](.cursor/agents/README.md).

`/verifier`, `/security-reviewer`, `/test-runner`, `/researcher`

### Rules (`.cursor/rules/`)
Persistent AI guidelines applied automatically or based on a certain condition. See the [full glossary](.cursor/rules/README.md).

### Skills (`.cursor/skills/`)
Specialized agent capabilities that commands can reference for domain-specific methodology. See the [full glossary](.cursor/skills/README.md).

## How to use

1. Download this repo
2. Copy the `.cursor/` folder into your project root, or any of the subfolders or files separately, if you have a `.cursor/` folder there already

**Commands** — invoke with `/command-name` in chat. They guide the AI through a structured task with a defined persona, steps, and output format.

**Skills** — domain knowledge that commands or agents reference for methodology. A command like `/create-presentation` pulls in the `presentation` skill automatically. You can also reference a skill manually (e.g. `@.cursor/skills/presentation.md`).

**Agents** — isolated sub-processes that run in parallel. Some trigger automatically (the parent agent delegates based on the task), others you invoke explicitly (`/researcher`, `/verifier`). They don't consume your main conversation's context.
