# design-ai-tools

A ready-made `.cursor/` setup for product designers and PMs who build with Cursor. Commands, rules, and skills — clone the repo, copy the folder, start using.

## What's inside

### Commands (`.cursor/commands/`)

Reusable AI workflows you invoke with `/command-name` in Cursor's chat. See the [full glossary](.cursor/commands/README.md).

Commands are designed as a **pipeline** — each step feeds into the next, taking you from idea to shipped, reviewed code:

```
/explore → /one-pager → /critique → /code-explore → /code-plan → /code-execute → /code-review → /code-review-peer → /document
```

Every predecessor is optional input, so each command also works standalone. The only hard dependency is `/code-execute`, which requires a plan from `/code-plan`.

**Product commands:** `/explore`, `/one-pager`, `/critique`
**Code commands:** `/code-explore`, `/code-plan`, `/code-execute`, `/code-review`, `/code-review-peer`, `/document`
**Standalone:** `/code-explain` (learning)

### Agents (`.cursor/agents/`)

Specialized subagents that run in parallel or get auto-delegated by the parent agent. They handle context-heavy work without bloating your main conversation.

| Agent | Triggers on |
|-------|------------|
| `/verifier` | After tasks marked done — validates implementations actually work |
| `/security-reviewer` | Proactively on auth, payments, API endpoints, user data |
| `/test-runner` | Proactively after code changes — runs tests and fixes failures |
| `/researcher` | During feature exploration or competitive analysis |

### Rules (`.cursor/rules/`)
Persistent AI guidelines applied automatically. Currently includes a general tone rule (be direct, push back, cite sources).

### Skills (`.cursor/skills/`)
Specialized agent capabilities. Work in progress.

## How to use

1. Clone or download this repo
2. Copy the `.cursor/` folder into your project root
3. Type `/` in Cursor's chat to see available commands
4. Run commands in pipeline order for a full feature flow, or pick any command individually
