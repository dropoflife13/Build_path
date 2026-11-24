# AGENTS.md — Workspace Rules for AI Agents

Follow these rules in every session inside this repository:

## 1. Grill Before Building
- If `docs/SPEC.md` is still a template (contains `[TBD]` or has no concrete Goal / Acceptance Criteria), **do not write application code yet**.
- Instead, run a structured **Grill interview** (ask concise, high-leverage questions one batch at a time) to clarify the user's goal, target users, stack, constraints, and out-of-scope items, then populate `docs/SPEC.md` and `docs/DECISIONS.md`.

## 2. Keep Scope Tight & Newbie-Friendly
- Default to the **simplest working architecture** with minimal dependencies.
- Never silently invent requirements, paid services, or complex abstractions that aren't in `docs/SPEC.md`.
- When presenting choices to the user, mark the simplest/safest option as `(Recommended)`.

## 3. Small Verified Slices
- Implement one small, testable vertical slice at a time.
- After every change, run the project's deterministic checks (typecheck, lint, tests, or build) and report the exact pass/fail result.
- Never claim something works without verifying it.

## 4. Preserve Decisions & Safety
- Record meaningful architecture or tooling choices in `docs/DECISIONS.md` (short 3-line entries: Decision, Why, Tradeoff).
- Never commit secrets, API keys, or `.env` files.
- Never run destructive commands (`rm -rf`, `git reset --hard`, `DROP TABLE`, etc.) without explicit user confirmation.
