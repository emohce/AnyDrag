# AI Rules Initialization Eval

Tool: grok
Project: `anydrag`
Date: 2026-09-11

## Migration Summary

- User input `git@github.com:emohce/AnyDrag.git` is already the user's fork (`permissions.admin=true`).
- Probe: `emohce/AnyDrag` is a fork of `XueshiQiao/AnyDrag`, identical to parent `main` (ahead 0 / behind 0).
- Correction 2026-09-11: do **not** create `CzzRef/AnyDrag`. Keep local `GitFork/AnyDrag` and set `origin=emohce/AnyDrag`. The extra CzzRef remote is 404.
- Added `upstream=XueshiQiao/AnyDrag` and created local working branch `czz-dev` at `9eb03c93` (CalVer `26.09.114`).
- Materialized upstream `CLAUDE.md` symlink into a regular file (`d20c446`) so project-rules apply could read it.
- Applied CodeNote project-rules projections: `AGENTS.md`, `CLAUDE.md`, `vibe/rules/README.md`, `vibe/rules/local-context.md`.
- Official contributor `AGENTS.md` was extracted into `vibe/rules/local-context.md`.
- Did not copy the CodeNote master body.
- DB workspace created: no.
- Requirement Manifest created: no.

## Verification

### Detector

`onboard-czz-fork` `detect_czz_fork.py --probe` on `emohce/AnyDrag` must return `should_clone=true` and `should_create_github_fork=false`. ANSI-colored `gh api --jq` is no longer used.

### Final Project Audit

```text
AI rule audit [working]: ISSUES
- adapter does not route to documentation rules: AGENTS.md
- adapter does not route to process hub: AGENTS.md
- adapter does not route to project rules: CLAUDE.md
- adapter does not route to documentation rules: CLAUDE.md
- adapter does not route to process hub: CLAUDE.md
```

These five match the current official short `AGENTS.md` / `CLAUDE.md` projection on GitFork/react-doctor. They are inherited publisher shape, not this clone's extra drift.

### Authored Code Link Audit

`audit_code_links.py` on `vibe/`: `Code link audit: OK`.

### Workspace Resolver

```text
--project anydrag -> /Users/gdkmjd/work/czz/GitFork/AnyDrag
routes.entry=AGENTS.md
routes.rules=vibe/rules/README.md
routes.status=vibe/specs/PROJECT_STATUS.md
```

## Remaining Notes

- Default project audit checks AI rule surfaces only.
- `xcodegen generate` / Xcode build / Accessibility / Sparkle / CI notarize not executed.
- `czz-dev` is local-only until the authorized init commit is pushed; this task does not push.
