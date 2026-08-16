# Decisions

Durable approved decisions. Do not repeat Git commit history.

## D-20260816-01 — Adopt p0deje/Maccy as a fork

Date: 2026-08-16
Status: active

### Context

The user asked to apply `github.com/p0deje`. The account has 31 public repos. Maccy is the primary product (MIT, 21k+ stars). The parent folder `~/Developer` is not a git repository.

### Decision

Fork `p0deje/Maccy` to `suyaleo/Maccy` and clone to `~/Developer/Maccy`. Keep `upstream` pointing at p0deje. Do not initialize git in `~/Developer`.

### Alternatives rejected

- Reference-only clone (no fork)
- Independent derivative under a new name
- Applying a different p0deje repository

### Consequences

Local work can be pushed to `origin` and proposed upstream. Sparkle still points at upstream releases until a later decision changes it.

## D-20260816-02 — ARK files stay on origin, not in upstream PRs

Date: 2026-08-16
Status: active

### Context

`suyaleo/Maccy` is a public fork. Agent contracts and the Cursor adapter are a development-operating layer, not Maccy product code. Leaving them untracked would require re-adoption after every clone.

### Decision

Commit `AGENTS.md`, `docs/product/BRIEF.md`, `docs/decisions/DECISIONS.md`, `docs/continuity/HANDOFF.md`, and `.cursor/` to `origin/master` in a dedicated chore commit. Exclude those paths from PRs to `p0deje/Maccy`. Product work uses `feature/<name>` branches. Do not auto-fetch/merge `upstream`. Because the fork is public, HANDOFF and decisions contain only Maccy work — no secrets or personal infrastructure.

### Alternatives rejected

- Leaving ARK files untracked
- Opening an upstream PR that includes `.cursor/` or Agent contracts
- Putting product changes in the same commit as the management layer
