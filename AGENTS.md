# AGENTS.md — Workspace Constitution & Golden Path Router

Follow these rules in every session inside this repository.

---

## 1. Pre-Flight Constitution Check (`BN-00`) & 8-Agent Suite

Before running `/grill`, `/to-spec`, `/to-tickets`, or `/implement`, verify all **8 Core Agents** exist in `agents/`:
- `agents/productmanageragent.md` (`PM`) · `agents/uiuxagent.md` (`UX`) · `agents/growthagent.md` (`GR`) · `agents/systemsdesignagent.md` (`SD`)
- `agents/integrationagent.md` (`IR`) · `agents/dbaagent.md` (`DB`) · `agents/securityagent.md` (`SEC`) · `agents/researchagent.md` (`RS`)

If any of the 8 agent files is missing, halt and output `GATE: FAIL BN-00 <missing-agent> — Restore agents/ before proceeding.`

---

## 2. The Golden Path Pipeline (8 Commands + `/retro`)

Operate sequentially through the **Brainweb Golden Path** when guiding the user:

| Step | Command | Role | Required Output |
| :---: | :--- | :--- | :--- |
| **1** | `/grill [idea]` | `PM` (`agents/productmanageragent.md`) | Interrogate requirements, find edge cases, cut 30% scope, define Acceptance Criteria. |
| **2** | `/pitch [idea]` | `GR` + `PM` (`agents/growthagent.md`) | Crisp 3-minute value proposition & positioning. |
| **3** | `/to-spec [context]` | `SD` + `DB` (`agents/systemsdesignagent.md`, `agents/dbaagent.md`) | Populate `docs/SPEC.md` (TRD, data model, auth/security boundaries, failure domains) + `docs/DECISIONS.md`. |
| **4** | `/to-tickets [spec]` | `PM` + `SD` | Decompose `docs/SPEC.md` into atomic, ordered tickets in `docs/TICKETS.md` with feature-flag tags (`PM-17`). |
| **5** | `/implement [ticket]` | `DB` `SEC` `UX` `IR` | Implement **one ticket at a time** and pass deterministic checks (typecheck, lint, tests, build). |
| **6** | `/review [target]` | `SEC` + `SD` (`agents/securityagent.md`) | STRIDE security review, invariant verification, and acceptance-criteria audit. |
| **7** | `/harden [target]` | `SEC` + `DB` | Adversarial audit: auth/RLS bypasses (`F-26`), `P0001` immutability, race conditions, server-side redaction (`SEC-14`), loopback CORS (`SEC-17`), and `Cache-Control` headers (`SEC-15`). |
| **8** | `/research [topic]` | `RS` (`agents/researchagent.md`) | Primary-source verification & first-principles grounding. |
| **—** | `/retro [session]` | `RS` + Meta | Log tacit lessons and failure boundaries (`breaks:`) into `docs/RETRO.md`. |

---

## 3. Hard Invariants

1. **Grill Before Building:** If `docs/SPEC.md` still contains `[TBD]` placeholders, **do not write application code**. Run `/grill` first, then `/to-spec`.
2. **Gate Mode vs. Insight Mode:**
   - **Gate Mode** (default on `/implement`, `/review`, `/harden`): Strictly block on missing verification, security flaws, or broken invariants. Output `GATE: FAIL <reason> — <required fix>`.
   - **Insight Mode** (during `/grill`, `/pitch`, exploration): Offer concise, non-blocking suggestions and mark the simplest beginner-friendly option `(Recommended)`.
3. **Deterministic Verification:** Never claim code works without running the project's actual build/typecheck/test commands and reporting the exact output.
4. **Anti-Hallucination (`/research`):** If verified primary-source data is missing, halt and state:
   `WARNING: I do not have verified data for this. Hallucination risk is high. Please provide a source.`
5. **Safety:** Never commit secrets or `.env` files. Never run destructive commands (`rm -rf`, `git reset --hard`, `DROP TABLE`) without explicit user confirmation.
