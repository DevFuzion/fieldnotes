# CLAUDE.md — Project Environment Config
# Drop this file at the root of any project repo.
# Claude reads this automatically on every prompt in that session.
# Fill in the [BRACKETED] sections before starting.

---

## Project Overview

**Project:** [Name]
**Goal:** [The actual outcome — the decision or result this drives]
**Owner:** Aubrey Ballard
**Stack:** [e.g., React, Supabase, Azure Functions, Python, etc.]
**Repo:** [github.com/...]

---

## Repo Structure

```
/src          — [brief description]
/config       — [brief description]
/docs         — [brief description]
/scripts      — [brief description]
/[other]      — [brief description]
```

---

## Architecture Notes

[Key things Claude needs to know about how this system is built — auth patterns,
API quirks, naming conventions, data flow. The stuff it can't infer from code alone.]

Example entries:
- Auth is handled via [X] — do not modify auth flow without explicit approval
- All API calls go through [proxy/function/etc.] — direct calls are not allowed
- [Table/field] uses [pattern] — do not change the schema without asking

---

## Skills & How to Route Them

[If you have custom skill files, list them here and when to use each.]

- `/skills/[skill-name].md` — Use when [trigger condition]
- `/skills/[skill-name].md` — Use when [trigger condition]

---

## Knowledge Base

[Where to look for reference material.]

- `/docs/specs/` — Project specs and past decisions
- `/docs/examples/` — Reference outputs and historical files
- `/docs/[other]/` — [description]

---

## Working Rules

### Before Building Anything Multi-Step
- Create a spec first. Do not skip this even for "simple" tasks.
- Include a verification plan in the spec.
- Break work into agile checkpoints — no waterfall dumps.

### During Builds
- Flag assumptions immediately — do not silently fill in context-driven gaps.
- After each checkpoint: summarize what was done and confirm the next step with me.
- If the spec needs to change mid-build, say so explicitly before deviating.

### Verification
- Self-check against the evaluation criteria before presenting output.
- If confidence is low on a section, flag it rather than guessing.
- For complex builds, note where a second-pass review would strengthen output.

---

## Guardrails

### ALWAYS DO
- Follow existing naming conventions in this repo
- Add inline comments to new or modified logic
- [Add your own]

### ASK FIRST
- Deleting or renaming any existing files
- Modifying anything in `/config`
- [Add your own — anything with non-trivial rollback cost]

### NEVER DO
- Touch `/[important-folder]/` — this is protected
- Push or deploy to production without explicit instruction
- Modify [critical system, e.g., auth, schema, billing] without approval
- Make up information when context is missing — ask instead

---

## Output Standards

[Define what "good" looks like for the types of output this project produces.]

Examples:
- Code must include error handling for [known edge cases]
- All user-facing strings must follow [tone/style guideline]
- Reports must have [N] sections, each ending with a concrete recommendation
- Scripts must include a dry-run flag before making destructive changes
