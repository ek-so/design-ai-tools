# Changelog

## Unreleased
- Added 4 subagents: `/verifier`, `/security-reviewer`, `/test-runner`, `/researcher`
- Built full feature pipeline: explore → one-pager → critique → code-explore → code-plan → code-execute → code-review → code-review-peer → document
- Each pipeline command references its predecessor as optional input (standalone-compatible)
- Rewrote all code commands (`code-explore`, `code-plan`, `code-execute`, `code-review`, `code-review-peer`, `code-explain`) with consistent template (Persona, Input, Mode, Steps, Output)
- Added `/code-review` and `/code-review-peer` commands
- Added `/document` to pipeline as final step
- Deleted `code-document.md` (superseded by `/document`)
- Updated commands glossary with all 10 commands, pipeline diagram, and standalone section
- Updated root `README.md` with project description, pipeline, agents, and setup instructions
- Added `.gitignore` and `future-ideas/` for unpublished drafts

## 2026-03-01 — New commands, skills, plugin manifest
- Added `/copy-review` command — reviews interface copy against a guidelines file and UX writing best practices
- Added `/create-presentation` command — builds presentation structure using the Kapterev dramaturgy method
- Added `presentation` skill (`.cursor/skills/presentation.md`) — first skill, referenced by `/create-presentation`
- Added `.cursor-plugin/plugin.json` — plugin manifest with all commands, agents, and metadata
- Added glossary READMEs for skills and rules (matching commands and agents format)
- Updated commands glossary: added standalone commands table, replaced dropdown template with markdown code block
- Updated root `README.md`: skills no longer "work in progress", added how commands/skills/agents work together
- Added `LInks.md` with links to skill/prompt collections (Github repos + websites)
- Removed `old_README.md`

## 2026-02-28 — Visual polish
- Added cover image (`assets/cover.png`)

## 2026-02-26 — Cleaned up non-code commands
- Rewrote `/explore`, `/critique`, `/one-pager`, `/document` with consistent structure (Persona, Input, Mode, Steps, Output)
- Added `/document` command for post-change documentation updates
- Removed `switch-mode` command (mode switching not supported programmatically in Cursor)

## 2026-02-25 — Added one-pager and modes experiment
- Added `/one-pager` command with three formats: Concept, Problem/Solution, Decision
- Experimented with mode-switching commands (later removed)

## 2026-02-24 — Initial release
- Added product commands: `/explore`, `/critique`
- Added code commands: `/code-explore`, `/code-plan`, `/code-execute`, `/code-explain`
- Added general rule (direct tone, push back, cite sources)
- Added commands glossary and template
