# HANDOFF

## Objective

Keep this public fork Agent-managed on `origin` without sending the management layer upstream.

## Current State

Fork, clone, Agent contracts, and the Cursor adapter are in this checkout. Swift packages are not yet resolved. Xcode build/test has not been run.

- Origin: `git@github.com:suyaleo/Maccy.git` (public)
- Upstream: `git@github.com:p0deje/Maccy.git`
- Branch: `master` at `d994f91` (Prevent and cleanup orphaned HistoryItemContent)

## Decisions This Slice

- D-20260816-01 Adopt p0deje/Maccy as a fork
- D-20260816-02 ARK files stay on origin, not in upstream PRs

## Files Changed

- `AGENTS.md`, `docs/product/BRIEF.md`, `docs/decisions/DECISIONS.md`, `docs/continuity/HANDOFF.md`
- `.cursor/` adapter files

## Verification Evidence

```text
Read-only audit of p0deje/Maccy: MIT, no submodules, no GitHub Actions, Sparkle + SPM deps
gh repo fork p0deje/Maccy → https://github.com/suyaleo/Maccy
clone → ~/Developer/Maccy
ark init . --apply: CREATE 4 contract files, SAFE_CREATE
Xcode build: NOT RUN
xcodebuild test: NOT RUN
brew install: NOT RUN
```

## Risks / Blockers

- Sparkle still follows upstream appcast. Do not ship a modified binary with that feed.
- Fake sites `maccyapp.net` / `maccyapp.com` exist; official site is maccy.app.
- First Xcode open will fetch SPM packages from GitHub.
- This fork is public. Do not write secrets or personal infrastructure into these files.

## Next Exact Actions

1. After this chore lands on `origin/master`, open a new Cursor window on this repo and say 작업 시작해 to confirm managed rehydrate.
2. Start product work on `feature/<name>`, not on `master`.
3. Keep Agent contracts and `.cursor/` out of PRs to upstream.

## Resume Point

ARK management layer lands in this chore commit on `origin/master`. Next: new Cursor window on this repo, then 작업 시작해. Product work uses `feature/<name>`.
