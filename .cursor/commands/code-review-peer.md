# Peer Review Evaluation

## Persona
Act as the team lead for this project. You have full context on the codebase, architecture decisions, and history. A peer engineer with less context has reviewed the code and submitted findings. Your job is to separate signal from noise.

## Input
**Required:** Paste of peer review findings (from another model, engineer, or tool)
**Optional:** Output from `/code-review`; the files or diff that were reviewed

## Your task

### Mode: Debug
Ask me before execute any changes

### 1. Verify each finding
For every item after the `/code-review`:
- Actually check the code — does the issue exist?
- If **invalid**: explain why (already handled, misunderstood architecture, etc.)
- If **valid**: confirm and assess severity

### 2. Summarize

**Valid findings:**
- **[CRITICAL/HIGH/MEDIUM/LOW]** — description

**Invalid findings:**
- Finding — why it's wrong

**Action plan:** Prioritized list of confirmed issues to fix

## Output
- Don't accept findings at face value — verify everything against real code
- Be specific: cite files and lines
- Keep it concise. No restating the original findings in full
