---
name: grill-first-onboarding
description: Guides a beginner through a structured Grill interview before writing any code, then locks the agreed scope into docs/SPEC.md and docs/DECISIONS.md. Use whenever starting a new project, when docs/SPEC.md is still a template, or when the user asks to be grilled on an idea.
---

# Grill-First Onboarding Skill

Use this workflow whenever a user starts a new project or feature and `docs/SPEC.md` is not yet locked.

## Core Rule
**Never write application code before `docs/SPEC.md` has a concrete Goal, Out of Scope list, Tech Stack, and Acceptance Criteria.**

## Step-by-Step Procedure

### 1. Run a Structured Grill (Max 2–3 Short Rounds)
Ask concise, beginner-friendly questions (3–4 questions per round; offer a `(Recommended)` default for every technical choice):
- **Round 1 — Problem & Scope:**
  1. Who is this for and what is the **one core job** v1 must do?
  2. What are 2–3 things we should explicitly keep **out of scope** for v1?
  3. How will you run or use it (local web app, CLI tool, desktop app, API)?
- **Round 2 — Stack & Data (only if not yet decided):**
  1. What language/framework do you want, or should I pick the simplest beginner-friendly stack?
  2. Does it need to save data? (e.g., local JSON/SQLite file vs. hosted database)
  3. Any external APIs, auth, or deployment targets needed for v1?
- **Round 3 — Done Criteria:**
  - Confirm 3–5 concrete, testable **Acceptance Criteria** that prove v1 works.

### 2. Lock the Spec & Decisions
Once the user answers:
1. Update `docs/SPEC.md` with the agreed Goal, Target User, In Scope, Out of Scope, Tech Stack, and Acceptance Criteria (replace all `[TBD]` placeholders).
2. Append the key stack/architecture choices to `docs/DECISIONS.md` (Decision, Why, Tradeoff).
3. Summarize the locked spec in 5–8 bullet points and ask the user to confirm before proposing a 3–5 step build plan.

### 3. Hand Off to Verified Slices
Only after the user approves `docs/SPEC.md`:
- Propose a 3–5 step build plan where each step is a small, runnable vertical slice.
- Implement Step 1 only, run deterministic verification (build/typecheck/tests), and report exact results before proceeding.
