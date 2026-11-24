# The Golden Path Pipeline — Command Reference & Prompts

Modeled on the **Brainweb 8-Command SDLC + `/retro`**. Use these commands in order inside **Antigravity**, **Claude Code**, or **Cursor**.

---

## 1. `/grill [idea]` (`PM`)
**Goal:** Interrogate the problem, uncover edge cases, cut 30% scope, and define Acceptance Criteria before writing code.
> **Prompt:** `Read AGENTS.md. Run /grill on my idea: [your idea]. Ask 3–4 concise questions per round, cut unnecessary v1 scope, and recommend the simplest beginner-friendly defaults.`

## 2. `/pitch [idea]` (`GR` + `PM`)
**Goal:** Synthesize the core value proposition and write a crisp 3-minute pitch.
> **Prompt:** `Run /pitch based on our /grill session. Give me a crisp 3-minute pitch covering the problem, target user, core solution, and why it's different.`

## 3. `/to-spec [context]` (`SD` + `DB`)
**Goal:** Author the Technical Requirements Document (`docs/SPEC.md`), data model, authorization boundaries, and failure domains, and log stack choices in `docs/DECISIONS.md`.
> **Prompt:** `Run /to-spec. Populate docs/SPEC.md and docs/DECISIONS.md from our /grill session. Do not write application code yet.`

## 4. `/to-tickets [spec]` (`PM` + `SD`)
**Goal:** Decompose `docs/SPEC.md` into sequential, atomic, verifiable implementation tickets in `docs/TICKETS.md`.
> **Prompt:** `Run /to-tickets. Break docs/SPEC.md into 3–7 small, ordered tickets in docs/TICKETS.md with explicit dependencies and a verification command for each.`

## 5. `/implement [ticket]` (`DB` `SEC` `UX` `IR`)
**Goal:** Implement **one ticket at a time** under deterministic verification (typecheck, lint, tests, build).
> **Prompt:** `Run /implement T-01. Implement only T-01 from docs/TICKETS.md, run the deterministic build/test check, and report the exact pass/fail result.`

## 6. `/review [target]` (`SEC` + `SD`)
**Goal:** Run a STRIDE security review, verify invariants, and check against `docs/SPEC.md` Acceptance Criteria.
> **Prompt:** `Run /review on our current implementation in Gate Mode. Check STRIDE threats, input validation, error handling, and Acceptance Criteria. Output GATE: FAIL for any blocking issue.`

## 7. `/harden [target]` (`SEC` + `DB`)
**Goal:** Adversarial audit—attack auth/RLS, probe race conditions, check server-side redaction, and verify `Cache-Control` headers.
> **Prompt:** `Run /harden on our current codebase. Act as an adversarial reviewer: try to break auth/permissions, race conditions, sensitive data leaks, and edge-case inputs.`

## 8. `/research [topic]` (`RS`) *(Use anytime)*
**Goal:** Deep-dive research grounded in primary sources and first principles—no hallucinated claims.
> **Prompt:** `Run /research on [topic]. Cite primary sources only. If verified data is missing, halt with "WARNING: I do not have verified data for this."`

## 9. `/retro [session]` (`RS` + Meta)
**Goal:** Post-implementation excavation—record tacit lessons and failure boundaries (`breaks:`) into `docs/RETRO.md`.
> **Prompt:** `Run /retro on this session. Append any recurring mistakes, fixes, and failure boundaries (WHEN <trigger> -> DO <action> | breaks: <boundary>) to docs/RETRO.md.`
