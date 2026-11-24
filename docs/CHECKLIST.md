# Newbie Pre-Flight & Shipping Checklist

## Before You Start (Day 1)
- [ ] **Git installed:** Run `git --version` in your terminal.
- [ ] **Repo cloned & opened:** Open this folder in Antigravity, Claude Code, or Cursor.
- [ ] **No secrets in Git:** Confirm `.env` is listed in `.gitignore` (already configured).

## Before Writing Any Code
- [ ] **Ran Grill session:** Used `/grill-me` (Antigravity) or `docs/GRILL-PROMPT.md`.
- [ ] **Locked `docs/SPEC.md`:** Zero `[TBD]` placeholders left; Out of Scope is clear.
- [ ] **Logged `docs/DECISIONS.md`:** Key stack choices recorded.
- [ ] **Committed spec:** `git commit -m "docs: lock initial project spec from grill session"`

## During Each Build Slice
- [ ] **One small step at a time:** Asked the AI to implement only 1 step from the plan.
- [ ] **Verified locally:** Ran the build/test/app command and saw it pass.
- [ ] **Committed checkpoint:** Saved working progress with `git commit`.
