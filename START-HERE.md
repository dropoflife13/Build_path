# START HERE — The Newbie Golden Path

Welcome. This starter follows the **Brainweb Golden Path**—a simple, step-by-step pipeline so you never get stuck in messy AI-generated code. **Always start with Step 1 (`/grill`).**

---

## Step 0: Pre-Flight Check (1 Minute)

Open [docs/CHECKLIST.md](docs/CHECKLIST.md) and confirm:
- [ ] Git is installed (`git --version`)
- [ ] This folder is open in **Antigravity**, **Claude Code**, or **Cursor**
- [ ] You have a rough 1–3 sentence idea of what you want to build

---

## Step 1: `/grill [idea]` — Interrogate & Cut Scope (5–10 Minutes)

Before writing a single line of code, make the AI grill you on your idea, find edge cases, and **cut 30% of unnecessary v1 scope**.

- **In Antigravity:** Type `/grill-me` (or `/grill`) followed by your 1–3 sentence idea.
  > Example: `/grill I want to build a personal expense tracker web app where I can log expenses and see my monthly total.`
- **In Claude Code / Cursor:** Copy and paste [docs/GRILL-PROMPT.md](docs/GRILL-PROMPT.md) with your idea at the bottom.

*(Tip: If you don't know the answer to a technical question, just say: **"recommend the simplest option for a beginner."**)*

---

## Step 2: `/pitch [idea]` — Clarify the Value *(Optional for tiny personal scripts)*

Ask the AI:
> `/pitch` — Summarize what we're building, who it's for, and why it matters in a crisp 3-minute pitch.

---

## Step 3: `/to-spec` — Lock the Technical Spec (`docs/SPEC.md`)

Ask the AI:
> `/to-spec` — Fill out `docs/SPEC.md` and `docs/DECISIONS.md` with our agreed scope, data model, auth/security boundaries, and Acceptance Criteria. Do not write application code yet.

Review `docs/SPEC.md`, then save your first checkpoint:
```bash
git add docs/SPEC.md docs/DECISIONS.md
git commit -m "docs: lock initial spec from grill session"
```

---

## Step 4: `/to-tickets` — Break Into Small Atomic Tickets (`docs/TICKETS.md`)

Ask the AI:
> `/to-tickets` — Break `docs/SPEC.md` into 3–7 small, ordered, verifiable tickets in `docs/TICKETS.md` with clear dependencies.

---

## Step 5: `/implement [ticket]` — Build One Ticket at a Time

Ask the AI:
> `/implement T-01` — Implement Ticket 1 only, run the build/typecheck/tests to verify it works, and show me the exact result.

Commit after every passing ticket:
```bash
git add .
git commit -m "feat: complete T-01"
```

---

## Steps 6 & 7: `/review` & `/harden` — Check Security & Edge Cases

Once your core tickets work:
- Run `/review` to check for security flaws (STRIDE), broken invariants, and missed acceptance criteria.
- Run `/harden` for an adversarial pass (bad inputs, auth bypasses, race conditions, leaked secrets, cache headers).

---

## Step 8 & `/retro` — Research Anytime, Capture Lessons After

- **`/research [topic]`** *(use anytime)*: Deep-dive with primary sources only—forces the AI to say *"I do not know"* instead of guessing.
- **`/retro`**: At the end of a session, log what broke and what worked into [docs/RETRO.md](docs/RETRO.md) using `WHEN <trigger> -> DO <action> | breaks: <boundary>`.

See [docs/GOLDEN-PATH.md](docs/GOLDEN-PATH.md) for copy-pasteable prompts for every command.
