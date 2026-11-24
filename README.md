# Build_path — The Agentic Golden Path Starter

A lean, clone-and-go starter template for **AI-assisted coding and agentic workflows**, modeled directly on the **Brainweb Golden Path Pipeline**. Built so even a complete beginner can clone it, open it in **Antigravity**, **Claude Code**, or **Cursor**, and go from a rough idea to a hardened, verified build—**always starting with `/grill` before writing a single line of code.**

---

## The Golden Path Pipeline (8 Commands + `/retro`)

Instead of typing *"build me an app"* and letting the AI guess 20 things wrong, follow the sequential pipeline:

| Step | Command | Role / Hat | Purpose & Output |
| :---: | :--- | :--- | :--- |
| **1** | `/grill [idea]` | Product (`PM`) | Interrogate requirements, find unhandled edge cases, cut 30% scope, lock Acceptance Criteria. |
| **2** | `/pitch [idea]` | Growth + Product (`GR` + `PM`) | Synthesize core value proposition and write a crisp 3-minute pitch. |
| **3** | `/to-spec [context]` | Systems + Data (`SD` + `DB`) | Author `docs/SPEC.md` (TRD): data model, authorization rules, and failure domains. |
| **4** | `/to-tickets [spec]` | Product + Systems (`PM` + `SD`) | Decompose `docs/SPEC.md` into atomic, verifiable tickets in `docs/TICKETS.md`. |
| **5** | `/implement [ticket]` | Builder (`DB` `SEC` `UX` `IR`) | Build **one ticket at a time** with deterministic verification (typecheck, lint, tests, build). |
| **6** | `/review [target]` | Security + Systems (`SEC` + `SD`) | Run a STRIDE security review and check invariants before merging. |
| **7** | `/harden [target]` | Security + Data (`SEC` + `DB`) | Adversarial audit: probe auth/RLS, race conditions, server-side redaction, and cache headers. |
| **8** | `/research [topic]` | Researcher (`RS`) | *(Use anytime)* Verify primary sources, triangulate citations, and enforce *"I do not know"* when unverified. |
| **—** | `/retro [session]` | Meta (`RS`) | Post-session excavation: log lessons and failure boundaries (`breaks:`) into `docs/RETRO.md`. |

---

## Quick Start (2 Minutes)

### 1. Clone this template
```bash
git clone https://github.com/dropoflife13/Build_path.git my-project
cd my-project
```
*(Optional: reset Git history so it's your own fresh repo)*
```bash
rm -rf .git
git init
git add .
git commit -m "chore: initialize from Build_path"
```

### 2. Open in your AI IDE
Open the folder in **Antigravity** (recommended), **Claude Code**, or **Cursor**.
- Antigravity automatically reads `AGENTS.md` and `.agents/skills/grill-first-onboarding/SKILL.md`.
- Claude Code / Cursor automatically reads `CLAUDE.md` (which points directly to `AGENTS.md`).

### 3. Follow `START-HERE.md`
Open **[START-HERE.md](START-HERE.md)** and start at **Step 1 (`/grill`)**.

---

## What's Inside

| File | Purpose |
| :--- | :--- |
| [`START-HERE.md`](START-HERE.md) | Step-by-step Day 1 walkthrough for beginners |
| [`AGENTS.md`](AGENTS.md) | Workspace constitution & Golden Path command router for AI agents |
| [`CLAUDE.md`](CLAUDE.md) | Compatibility bridge for Claude Code and Cursor |
| [`.agents/skills/grill-first-onboarding/SKILL.md`](.agents/skills/grill-first-onboarding/SKILL.md) | Antigravity skill that guides beginners through `/grill` -> `/to-spec` -> `/to-tickets` |
| [`docs/GOLDEN-PATH.md`](docs/GOLDEN-PATH.md) | Full reference & copy-pasteable prompts for all 8 commands + `/retro` |
| [`docs/GRILL-PROMPT.md`](docs/GRILL-PROMPT.md) | Quick copy-paste `/grill` starter prompt |
| [`docs/SPEC.md`](docs/SPEC.md) | Technical Requirements Document (TRD) populated by `/to-spec` |
| [`docs/TICKETS.md`](docs/TICKETS.md) | Atomic implementation tickets populated by `/to-tickets` |
| [`docs/DECISIONS.md`](docs/DECISIONS.md) | Lightweight ADR log so the AI never undoes earlier choices |
| [`docs/RETRO.md`](docs/RETRO.md) | Post-session lessons & failure boundaries (`breaks:`) populated by `/retro` |
| [`docs/CHECKLIST.md`](docs/CHECKLIST.md) | Pre-flight & per-ticket verification checklist |
