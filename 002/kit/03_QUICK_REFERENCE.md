# The Karpathy Method — Quick Reference

## The Core Problem
AI is brilliant at measurable things. It fails at context-driven things — because it
has no signal for what it doesn't know that you know. Your job is to bridge that gap.

---

## The 3 Layers

### Layer 1 — The Spec
*Deliver your understanding to Claude in a format it can use.*

| ❌ Wrong | ✅ Right |
|---|---|
| "Create an end-of-month report" | "Interview me to find the goal, then spec it out" |
| Big task handed off at once | Small scoped chunks with checkpoints |
| Vague deliverable | Precise output with explicit criteria |

**Key moves:**
- Have Claude interview you to surface the real goal (not just the task)
- Be agile: tight scope → review → adjust → repeat
- Be precise: every assumption Claude makes is a chance to drift

---

### Layer 2 — The Verifier
*Define what good looks like before Claude touches anything.*

| ❌ Wrong | ✅ Right |
|---|---|
| "Make this better" | "Output must have X, Y, Z — evaluate against these" |
| One model, no check | Use a second model or tool as critic |
| No external signal | Connect to live system / pull reference files |

**Key moves:**
- Set evaluation criteria up front, in concrete terms
- Use a second model as a critic (e.g., run output by a different AI or linter)
- Pull in external signal — historical files, live system output, test results

> "If Claude has a feedback loop, it will 2–3x the quality of the final result."
> — Boris Cherny, creator of Claude Code

---

### Layer 3 — The Environment
*Build a workshop that improves over time.*

| Component | What it does |
|---|---|
| `CLAUDE.md` | Auto-injected context — repo structure, rules, architecture notes |
| Knowledge base | Folder of your own reference data Claude can pull from |
| Skills | Reusable task handbooks for repeated work |
| Guardrails | Always do / Ask first / Never do — enforced at tool level, not just prompt level |

**Key insight:** Prompt-level rules are requests. Tool-level hooks are rules.
If something can't be wrong, enforce it at the environment level.

---

## The Mental Model

**You are not talking to a person.** Yelling, pleading, and vague direction don't work.
The only lever you actually have is **verification** — giving it precise criteria to
evaluate against.

Think: robot librarian. Brilliant at what's in the library. Confidently wrong about
what isn't. It doesn't know when it's missing a book.

---

## The One Thing

> "You can outsource your thinking, but you can't outsource your understanding."
> — Andrej Karpathy

The three layers only work if *you* understand the goal well enough to define it.
AI amplifies your direction. It doesn't replace having one.

---

## Project Startup Checklist

- [ ] Run goal discovery interview before writing a single line
- [ ] Approve the spec before building starts
- [ ] Define evaluation criteria up front
- [ ] Set guardrails (always/ask/never) before any agentic work
- [ ] Break work into agile checkpoints — no waterfall
- [ ] Pull in reference material or live signal where it helps verify output
- [ ] Put a `CLAUDE.md` at the repo root
