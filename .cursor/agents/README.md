# Agents glossary

## What are agents?

Agents (subagents) are specialized AI assistants that run in their own context window. The parent agent delegates tasks to them automatically or you invoke them explicitly with `/agent-name`. They work in parallel, don't bloat your main conversation, and return a summary when done.

## How they work

- Each agent has its own context — long research or test runs don't eat your main conversation's memory
- The parent agent reads the `description` field to decide when to delegate automatically
- Agents can run in **foreground** (blocks until done) or **background** (returns immediately)
- Agents can't launch other agents (single level only)

## All agents

| Agent | Model | Description |
|-------|-------|-------------|
| `/verifier` | fast | Validates completed work. Checks that implementations actually function, runs tests, catches edge cases. Use after tasks are marked done. |
| `/security-reviewer` | inherit | Security auditor. Checks for injection, auth bypass, hardcoded secrets, input validation, RLS gaps. Triggers proactively on auth, payments, API endpoints, or user data. |
| `/test-runner` | fast | Runs tests after code changes. Analyzes failures, fixes them while preserving test intent, reports results. Triggers proactively. |
| `/researcher` | inherit | Researches topics via web search and codebase analysis. Finds 5-7 sources, summarizes, flags contradictions. Read-only. Use during `/explore` or `/critique`. |

## How to invoke

**Automatically** — the parent agent delegates based on the task and agent descriptions. Phrases like "use proactively" in the description encourage this.

**Explicitly** — type the agent name as a slash command:
```
/verifier confirm the auth flow is complete
/researcher find competitors for X
```

## Configuration fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | No | Lowercase + hyphens. Defaults to filename. |
| `description` | No | Tells the parent agent **when** to delegate. Most important field. |
| `model` | No | `fast`, `inherit`, or a specific model ID. |
| `readonly` | No | `true` restricts write permissions. |
| `is_background` | No | `true` runs without blocking. |

## Agents vs commands

| Use **commands** when... | Use **agents** when... |
|---|---|
| Single-purpose, one-shot task | Multi-step work needing context isolation |
| You want to invoke it explicitly | You want automatic delegation |
| Quick, repeatable action | Long-running or parallel work |
| Output goes directly to you | Output feeds back into the parent agent |

## Creating a new agent

Add a markdown file to `.cursor/agents/` with YAML frontmatter:

```markdown
---
name: agent-name
description: When to use this agent. Be specific.
model: inherit
---

Your system prompt here. Keep it concise — long prompts make agents slower, not smarter.
```

Best practices:
- Start with 2-3 focused agents, not dozens of generic ones
- Invest in the `description` — it determines when delegation happens
- Keep prompts short and specific
- Avoid generic agents like "helps with coding"
