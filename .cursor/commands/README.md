# Commands glossary

| Command | Mode | Description | Input |
|---------|------|-------------|-------|
| `/explore` | Ask | Product discovery — restates the concept, validates the problem, maps 5-7 competitors, surfaces risks. | **Required:** product idea or feature. **Optional:** competitors, image, PRD. |
| `/critique` | Ask | Senior leadership stress-test of an idea — challenges need, approach, technical/business/strategic risk. Rates 1-5. | **Required:** product idea or initiative. **Optional:** competitors, mockups, PRD, metrics. |
| `/one-pager` | Agent | Writes a product one-pager in one of three formats: Concept, Problem/Solution, or Decision. Asks to confirm format first. | **Required:** feature or product idea. **Optional:** explore output, business context. |
| `/document` | Agent | Updates documentation after code changes. Reads actual code, never trusts existing docs. | **Required:** git diff, commits, or change description. **Optional:** affected files, existing docs. |
| `/code-explore` | — | Analyzes codebase to understand how a feature fits — dependencies, structure, edge cases. No implementation. | None. Uses codebase and conversation context. |
| `/code-plan` | — | Produces a structured implementation plan with progress tracking. No implementation. | Requires prior exploration/discussion context. |
| `/code-execute` | Agent | Implements precisely as planned, updating the tracking document as it goes. | Requires a plan from `/code-plan`. |
| `/code-explain` | — | Three-level explanation (core concept, how it works, deep dive) tailored to a technical PM audience. | A concept or pattern from the current work. |

## How to create a good command?
- 2500 characters max (including spaces and formatting)
- 

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