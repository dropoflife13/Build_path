# Architectural Decisions (`docs/DECISIONS.md`)

> A lightweight log of *why* we made key choices. Keeps both humans and AI agents from accidentally undoing earlier decisions.

## Template
```markdown
### ADR-001: [Short Title]
- **Date:** YYYY-MM-DD
- **Decision:** What we chose.
- **Why:** The reason this fits v1 best.
- **Tradeoff:** What we intentionally gave up or deferred.
```

---

### ADR-000: Grill-First Development Workflow
- **Date:** 2026-11-24
- **Decision:** Lock `docs/SPEC.md` via a structured Grill interview before writing application code.
- **Why:** Prevents AI hallucinated requirements, over-engineering, and wasted rework.
- **Tradeoff:** Adds 5–10 minutes upfront before the first line of code is written.
