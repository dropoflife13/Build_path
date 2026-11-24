# START HERE — The Newbie Golden Path

Welcome. Follow these **4 steps in order**. Do not skip Step 2—it is the single biggest difference between a messy AI project and a clean one.

---

## Step 1: Pre-Flight Check (1 Minute)

Open [docs/CHECKLIST.md](docs/CHECKLIST.md) and confirm you have:
- [ ] Git installed (`git --version`)
- [ ] This folder opened in **Antigravity**, **Claude Code**, or **Cursor**
- [ ] A rough 1–3 sentence idea of what you want to build

---

## Step 2: Start With a Grill (5–10 Minutes)

Before asking the AI to write any code, make it **grill you** on your idea.

- **In Antigravity:** Type `/grill-me` followed by your 1–3 sentence idea.
  > Example: `/grill-me I want to build a simple personal expense tracker web app where I can log expenses and see my monthly total.`
- **In Claude Code / Cursor / Any other AI chat:** Copy and paste the prompt from [docs/GRILL-PROMPT.md](docs/GRILL-PROMPT.md) and add your 1–3 sentence idea at the bottom.

Answer the AI's questions one by one. If you don't know the answer to a technical question, just say *"recommend the simplest option for a beginner."*

---

## Step 3: Lock Your Spec & Decisions (2 Minutes)

At the end of the Grill session, tell the AI:
> *"Fill out `docs/SPEC.md` and `docs/DECISIONS.md` with everything we just agreed on. Do not write application code yet."*

Review `docs/SPEC.md` quickly:
- Does **Goal** match what you actually want?
- Is **Out of Scope** clear so the AI doesn't overbuild?
- Are the **Acceptance Criteria** easy to test?

Once it looks right, commit your spec:
```bash
git add docs/SPEC.md docs/DECISIONS.md
git commit -m "docs: lock initial project spec from grill session"
```

---

## Step 4: Build One Small Slice at a Time

Now tell the AI:
> *"Read `AGENTS.md` and `docs/SPEC.md`. Propose a 3–5 step build plan, then implement Step 1 only and verify it works."*

**Golden Rules while building:**
1. **One slice at a time:** Never ask the AI to build the whole app in one shot.
2. **Verify every slice:** Run the build/test/app after each step before moving on.
3. **Commit working checkpoints:** Every time something works, run `git commit` so you can always roll back safely.
4. **Update `docs/DECISIONS.md`:** Whenever you change direction, have the AI log *why* in `docs/DECISIONS.md`.
