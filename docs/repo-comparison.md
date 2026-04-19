# Repo comparison — HeyGen Hyperframes vs Nate's Student Kit

Captured 2026-04-19 when we evaluated which upstream base to use for Raven Design Studio.

## TL;DR — We use both, in distinct roles

| Repo | Role | Why |
|---|---|---|
| `heygen-com/hyperframes` | Engine — installed via `npx hyperframes` | Apache 2.0, actively maintained, upgrades cleanly via npm. We do not fork it. |
| `nateherkai/hyperframes-student-kit` | Reference library for patterns | MIT on code. We mine it for folder structure, skills set, and discipline. Brand assets are AIS property and are not reused. |
| `Raven_Design_Studio` (this repo) | Where we actually work | Raven-branded from day one. |

## HeyGen Hyperframes (the engine)

- Apache 2.0 license, published to npm as `@hyperframes/cli`, `@hyperframes/core`, `@hyperframes/engine`, `@hyperframes/producer`, `@hyperframes/player`, `@hyperframes/studio`, `@hyperframes/shader-transitions`.
- Node 22+, Bun required for workspace ops. TypeScript strict, oxlint + oxfmt tooling.
- Rendering: Puppeteer + Chrome's BeginFrame API for deterministic frame-step. FFmpeg external.
- CLI verbs: `init`, `preview`, `lint`, `validate`, `render`, `transcribe`, `tts`, `add`, `catalog`, `doctor`, `info`, `benchmark`, `skills`, `browser`.
- Registry of 50+ reusable blocks (data-chart, flowchart, social overlays, 3D UI reveals, 20+ shader transitions, cinematic effects).
- 8 starter templates accessible via `hyperframes init`.
- Bundled with 5 vercel-labs skills for Claude Code / Cursor: `hyperframes`, `hyperframes-cli`, `hyperframes-registry`, `gsap`, `website-to-hyperframes`.

## Nate Herkai's Student Kit (reference)

- MIT license on code. Brand assets (AIS logos, tokens) explicitly NOT licensed for reuse.
- 12 finished reference videos under `video-projects/`. Structure: `index.html` + `compositions/` + `assets/` + `renders/` + `meta.json` + `hyperframes.json` + optional `STORYBOARD.md` / `HANDOFF.md` / `NOTES.md`.
- 7 skills under `.claude/skills/`: the 5 vercel-labs ones plus `make-a-video` and `short-form-video`. Pinned via `skills-lock.json`.
- `MOTION_PHILOSOPHY.md` (635 lines) — motion discipline derived from the "Infinite — Global Payments" ad. Useful as a framework; aesthetic is rejected for Raven.
- Minimal-coupling reference videos (best starting points): `claude-edit-intro`, `hyperframes-sizzle`, `clickup-demo`, `first-agent-promo`.
- Heavy-AIS reference videos (skip): `aisoc-*`, `golden-ratio-demo`.

## What Raven Design Studio took from each

From **HeyGen Hyperframes** (engine-level, runtime-loaded):
- The CLI. We call it via `npx hyperframes`.
- The 5 vercel-labs skills — copied into `.claude/skills/` with versions pinned in `skills-lock.json`.
- The registry catalog (accessible via `hyperframes add`).

From **Nate's Student Kit** (pattern-level, authored-here):
- Folder convention: `video-projects/<slug>/` with `index.html`, `compositions/`, `assets/`, `renders/`, `meta.json`, `hyperframes.json`, `STORYBOARD.md`.
- Skills list: same 7 Nate carried (5 upstream + `make-a-video` + `short-form-video`).
- Engineering discipline from `MOTION_PHILOSOPHY.md` — adopted into our own `MOTION_PHILOSOPHY.raven.md` with taste-layer rewritten.

From **neither** (fresh authoring):
- `DESIGN.raven.md` — sourced from the Claude Design export's shipped `index.css`, `siteContent.ts`, and the chat transcript.
- `brand-tokens.css` — ported from the Claude Design `index.css` shipped state.
- The Mokoto wordmark font (Sammy holds commercial license).
- `CLAUDE.md` — custom to Raven's workflow and guardrails.
