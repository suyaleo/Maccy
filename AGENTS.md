# AGENTS.md

Project-specific Agent constitution. Keep this file short and stable.

Do not accumulate implementation history here.

## Identity

- Name: Maccy
- Purpose: Lightweight macOS clipboard manager (fork of p0deje/Maccy)
- Canonical checkout: `~/Developer/Maccy/`
- Origin: `git@github.com:suyaleo/Maccy.git`
- Upstream: `git@github.com:p0deje/Maccy.git`

## Read first

1. `AGENTS.md` (this file)
2. `docs/product/BRIEF.md`
3. `docs/decisions/DECISIONS.md`
4. `docs/continuity/HANDOFF.md`
5. `git status`, recent `git log`, relevant `git diff`
6. files that will actually be modified

## Constraints

- Inspect before modifying.
- Repository evidence outranks Agent memory.
- One Primary Agent owns the active slice.
- Do not invent secrets, licenses, or remote repository settings.
- Keep the MIT license notice (Copyright Alex Rodionov).
- Do not change Sparkle update URL or signing keys without an explicit decision.
- Official site is https://maccy.app — do not use maccyapp.net or maccyapp.com.
- This origin is a **public** fork. Do not put secrets, credentials, personal IPs, NAS paths, private-repo names, or other-project state in Git, HANDOFF, or `.cursor/`.
- Agent contracts and `.cursor/` are a fork-local management layer. Commit them to `origin`. Never include them in PRs to `upstream`.

## Commands

```text
lint:    swiftlint lint --strict
typecheck: NOT APPLICABLE (Xcode / Swift)
test:    xcodebuild test -project Maccy.xcodeproj -scheme Maccy -testPlan Maccy
build:   xcodebuild -project Maccy.xcodeproj -scheme Maccy -configuration Debug
```

Xcode resolves Swift packages on first open. Do not run `brew install maccy` against this checkout.

## Prohibited

- force push / rewrite shared history without Level 3 approval
- production deploy, public exposure, license change without Level 3 approval
- silent overwrite of existing user files
- storing secrets in Git, handoff, or prompt history
- shipping a Sparkle feed that still points at upstream while using a different binary

## Verification gate

Use the repository's discovered test/build commands above.

Mark skipped layers `NOT RUN` or `NOT APPLICABLE`.

`./bin/ark verify` is NOT APPLICABLE in this product checkout (kit lives in `~/Developer/agent-rules-kit`).

## Continuity

Update `docs/continuity/HANDOFF.md` before context loss, provider switch, or session end.
