# Project Kickoff Prompt
# Paste this at the start of any new project session.
# Fill in the [BRACKETED] sections or let Claude interview you.

---

## STEP 1 — Goal Discovery (run this first)

```
Before we build anything, I need you to interview me to identify:
1. The actual GOAL (the decision or outcome this drives — not just the task)
2. Who the end user/audience is
3. What "done" looks like in concrete, measurable terms
4. What I already know that you'd have no way of knowing (context, constraints, quirks)

Ask me one question at a time. Do not proceed to the spec until I've confirmed the goal.
```

---

## STEP 2 — Spec Creation

After the interview, use this prompt to generate the spec:

```
Based on what I've told you, create a tightly scoped project spec that includes:

1. **Goal** — The actual outcome, not the task
2. **Scope** — What is explicitly IN and OUT of scope
3. **Deliverables** — Concrete, specific outputs (not vague descriptions)
4. **Evaluation Criteria** — Precise definition of what "good output" looks like
   (e.g., not "make it look good" — instead "must have 3 sections, each ending with a recommendation")
5. **Key Assumptions** — List any assumptions you're making so I can catch drift early
6. **Checkpoints** — Break this into small agile stages with review points, not one waterfall dump
7. **What I should verify explicitly** — Force me to confirm the critical decisions before you build

Bias toward smaller, more compartmentalized specs. Make me verify key decisions
explicitly before moving forward. Do not start building until I approve this spec.
```

---

## STEP 3 — Verification Layer

Before executing, add this verification contract:

```
Before you begin, outline:
1. The evaluation criteria you'll use to self-check your output
2. Any external data or references I should pull in to help you verify (examples, historical files, live system output)
3. Points in the build where you'll pause and ask me to review before continuing
4. If this is a complex build: flag where a second pass or external check (different model, linter, test, etc.) would add confidence

If at any point you're unsure whether output meets the criteria, stop and ask — do not guess or fill in.
```

---

## STEP 4 — Guardrails (define before any agentic work)

```
Before you touch any files or make any changes, confirm:

ALWAYS DO (run on autopilot):
- [e.g., follow existing naming conventions, add comments to new functions]

ASK FIRST (pause and confirm with me):
- [e.g., deleting files, changing schema, modifying anything in /config]

NEVER DO (hard stop — do not proceed even if asked):
- [e.g., touch /important-dont-edit/, push to prod, modify auth logic without explicit approval]
```

---

## STEP 5 — Agile Execution Rules

```
Rules for this session:
- Work in small, reviewable chunks — do not complete everything and present a final dump
- After each checkpoint, summarize what was done and what's next before continuing
- If you realize the spec needs to change mid-build, flag it — don't silently deviate
- Do not make assumptions about context-driven things (business logic, user behavior, edge cases) — ask
```
