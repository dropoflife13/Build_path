# AGENTS.md — Workspace Constitution & Golden Path Router

Follow these rules in every session inside this repository.

---

## 1. The Golden Path Pipeline (8 Commands + `/retro`)

Operate sequentially through the **Brainweb Golden Path** when guiding the user:

| Step | Command | Role | Required Output |
| :---: | :--- | :--- | :--- |
| **1** | `/grill [idea]` | `PM` | Interrogate requirements, find edge cases, cut 30% scope, define Acceptance Criteria. |
| **2** | `/pitch [idea]` | `GR` + `PM` | Crisp 3-minute value proposition & positioning. |
| **3** | `/to-spec [context]` | `SD` + `DB` | Populate `docs/SPEC.md` (TRD, data model, auth/security boundaries, failure domains) + `docs/DECISIONS.md`. |
| **4** | `/to-tickets [spec]` | `PM` + `SD` | Decompose `docs/SPEC.md` into atomic, ordered tickets in `docs/TICKETS.md`. |
| **5** | `/implement [ticket]` | `DB` `SEC` `UX` `IR` | Implement **one ticket at a time** and pass deterministic checks (typecheck, lint, tests, build). |
| **6** | `/review [target]` | `SEC` + `SD` | STRIDE security review, invariant verification, and acceptance-criteria audit. |
| **7** | `/harden [target]` | `SEC` + `DB` | Adversarial audit: auth/RLS bypasses, race conditions, server-side redaction, cache-control headers. |
| **8** | `/research [topic]` | `RS` | Primary-source verification & first-principles grounding. |
| **—** | `/retro [session]` | `RS` + Meta | Log tacit lessons and failure boundaries (`breaks:`) into `docs/RETRO.md`. |

---

## 2. Hard Invariants

1. **Grill Before Building:** If `docs/SPEC.md` still contains `[TBD]` placeholders, **do not write application code**. Run `/grill` first, then `/to-spec`.
2. **Gate Mode vs. Insight Mode:**
   - **Gate Mode** (default on `/implement`, `/review`, `/harden`): Strictly block on missing verification, security flaws, or broken invariants. Output `GATE: FAIL <reason> — <required fix>`.
   - **Insight Mode** (during `/grill`, `/pitch`, exploration): Offer concise, non-blocking suggestions and mark the simplest beginner-friendly option `(Recommended)`.
3. **Deterministic Verification:** Never claim code works without running the project's actual build/typecheck/test commands and reporting the exact output.
4. **Anti-Hallucination (`/research`):** If verified primary-source data is missing, halt and state:
   `WARNING: I do not have verified data for this. Hallucination risk is high. Please provide a source.`
5. **Safety:** Never commit secrets or `.env` files. Never run destructive commands (`rm -rf`, `git reset --hard`, `DROP TABLE`) without explicit user confirmation.
