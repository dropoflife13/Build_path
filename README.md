# Agentic Golden Path

A lean, zero-bloat starter template for **AI-assisted coding and agentic workflows**. Built so even a complete beginner can clone it, open it in **Antigravity** (or Claude Code / Cursor), and go from a rough idea to a clean, verified build—**always starting with a Grill session before writing a single line of code.**

## Why "Grill First"?

Most beginners fail with AI coding for one reason: they type *"build me an app"* and let the AI guess 20 things wrong.  
The **Golden Path** flips that:

1. **Grill first:** Make the AI interview *you* until every ambiguity, scope boundary, and edge case is resolved.
2. **Lock the spec:** Save the answers into `docs/SPEC.md` and `docs/DECISIONS.md`.
3. **Build in small verified slices:** Only write code once the spec is clear, and verify every step.

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
git commit -m "chore: initialize from agentic-golden-path"
```

### 2. Open in your AI IDE
Open the folder in **Antigravity** (recommended), **Claude Code**, or **Cursor**.
- Antigravity automatically reads `AGENTS.md` and `.agents/skills/grill-first-onboarding/SKILL.md`.
- Claude Code / Cursor automatically reads `CLAUDE.md` (which points directly to `AGENTS.md`).

### 3. Follow `START-HERE.md`
Open **[START-HERE.md](START-HERE.md)** and run your first **Grill session** (`/grill-me` in Antigravity, or paste [docs/GRILL-PROMPT.md](docs/GRILL-PROMPT.md)).

---

## What's Inside (And Why)

| File | Purpose |
| :--- | :--- |
| [`START-HERE.md`](START-HERE.md) | Step-by-step Day 1 walkthrough for beginners |
| [`AGENTS.md`](AGENTS.md) | Core rules every AI agent must follow in this repo (Grill before coding, no silent guessing) |
| [`CLAUDE.md`](CLAUDE.md) | Compatibility bridge for Claude Code and Cursor |
| [`.agents/skills/grill-first-onboarding/SKILL.md`](.agents/skills/grill-first-onboarding/SKILL.md) | Antigravity skill that runs the structured Grill interview and fills out `docs/SPEC.md` |
| [`docs/GRILL-PROMPT.md`](docs/GRILL-PROMPT.md) | Copy-pasteable Grill prompt if you aren't using `/grill-me` |
| [`docs/SPEC.md`](docs/SPEC.md) | Your single source of truth for what you're building (and what you're *not* building) |
| [`docs/DECISIONS.md`](docs/DECISIONS.md) | Lightweight log of key technical choices so the AI never undoes them |
| [`docs/CHECKLIST.md`](docs/CHECKLIST.md) | Newbie pre-flight & shipping checklist |
