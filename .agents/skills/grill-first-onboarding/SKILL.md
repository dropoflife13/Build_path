---
name: grill-first-onboarding
description: Guides a beginner through the Brainweb Golden Path pipeline starting with /grill, then /pitch, /to-spec, /to-tickets, /implement, /review, /harden, /research, and /retro. Use whenever starting a new project, when docs/SPEC.md is still a template, or when the user invokes any Golden Path command.
---

# Brainweb Golden Path Onboarding Skill

Use this workflow whenever a user starts a new project or invokes any Golden Path command (`/grill`, `/pitch`, `/to-spec`, `/to-tickets`, `/implement`, `/review`, `/harden`, `/research`, `/retro`).

## Core Rule
**Never write application code before `/grill` is complete and `docs/SPEC.md` has a concrete Goal, Out of Scope list, Tech Stack, and Acceptance Criteria.**

## Pipeline Sequence

1. **`/grill [idea]` (`PM`):** Ask 3–4 concise, plain-English questions per round (max 2–3 rounds). Cut ~30% unnecessary v1 scope. Offer a `(Recommended)` beginner-friendly default for every technical choice.
2. **`/pitch [idea]` (`GR` + `PM`):** *(Optional)* Summarize the core value proposition in a crisp 3-minute pitch.
3. **`/to-spec` (`SD` + `DB`):** Populate `docs/SPEC.md` (Goal, Target User, In/Out of Scope, Data/Auth boundaries, Stack, Acceptance Criteria) and log key stack choices in `docs/DECISIONS.md`. Ask the user to confirm before coding.
4. **`/to-tickets` (`PM` + `SD`):** Break `docs/SPEC.md` into 3–7 atomic, ordered tickets in `docs/TICKETS.md`, each with an explicit verification command.
5. **`/implement [ticket]` (`DB` `SEC` `UX` `IR`):** Implement **one ticket at a time**, run deterministic verification (typecheck/lint/tests/build), and report exact pass/fail results.
6. **`/review [target]` (`SEC` + `SD`):** Run a Gate Mode STRIDE security & invariant review; output `GATE: FAIL <reason> — <fix>` for any blocker.
7. **`/harden [target]` (`SEC` + `DB`):** Run an adversarial pass (auth/RLS bypasses, race conditions, sensitive data leaks, cache headers).
8. **`/research [topic]` (`RS`):** *(Anytime)* Ground in primary sources only; halt with `"WARNING: I do not have verified data for this. Hallucination risk is high. Please provide a source."` if unverified.
9. **`/retro` (`RS` + Meta):** Append tacit lessons and failure boundaries (`WHEN <trigger> -> DO <action> | breaks: <boundary>`) to `docs/RETRO.md`.
