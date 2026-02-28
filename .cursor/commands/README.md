# Commands glossary

## Pipeline

Commands form a feature pipeline — each step feeds into the next. Every predecessor is optional input (except `/code-execute`, which requires a plan), so each command also works standalone.

```
/explore → /one-pager → /critique → /code-explore → /code-plan → /code-execute → /code-review → /code-review-peer
```

## All commands

| Command | Mode | Description |
|---------|------|-------------|
| `/explore` | Ask | Product discovery — validates the problem, maps 5-7 competitors, surfaces risks. |
| `/one-pager` | Agent | Writes a product one-pager (Concept, Problem/Solution, or Decision format). |
| `/critique` | Ask | Senior leadership stress-test — challenges need, approach, and risk. Rates 1-5. |
| `/code-explore` | Ask | Analyzes codebase to understand how a feature fits — dependencies, structure, edge cases. |
| `/code-plan` | Plan | Produces a structured implementation plan with progress tracking. |
| `/code-execute` | Agent | Implements the plan step by step, updating the tracking document as it goes. |
| `/code-review` | Ask | Thorough code review focused on production readiness and security. |
| `/code-review-peer` | Ask | Evaluates peer review findings — verifies each against real code, separates signal from noise. |

**Standalone (not part of the pipeline):**

| Command | Mode | Description |
|---------|------|-------------|
| `/code-explain` | Ask | Three-level explanation (core concept, how it works, deep dive) for a technical PM audience. |
| `/document` | Agent | Updates documentation after code changes. Reads actual code, never trusts existing docs. |

## How to create a good command?
- 2500 characters max (including spaces and formatting)
- Use the template below
- Keep it very simple and to the point, reference results of other commands that might add useful context

<details>
<summary><strong>New command template</strong></summary>

# Command name

## Persona
Act as a... 

## Input
**Required:** ... 
**Optional:** ...

## Your task

### Mode: Ask / Agent / Plan / Debug
E.g. Don't make any changes until my explicit approval
(in the future might be useful to switch modes, when this is available in Cursor)

### 1. Step one name
- ...
- ...

### 2. Step two name
- ...
- ...

### N. Step N name
- ...
- ...

## Output
...

</details>