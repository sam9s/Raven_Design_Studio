# CLAUDE.md — Raven Design Studio

Read this at the start of every session. It teaches future Claude Code sessions the shape of this project and the brand guardrails they must respect.

## What this project is

Raven Design Studio is an internal AI-video-editing studio for **Raven Solutions** (https://ravensolutions.in). It uses **HeyGen Hyperframes** (installed via `npx hyperframes`, not cloned) as the rendering engine, driven by Claude Code, to produce advertisement videos, shots, YouTube explainers, and short-form content for Raven's own marketing — not for clients.

The studio is **local-only**. No VPS deployment. GitHub is the offsite backup.

The owner is Samret Singh (goes by "Sammy"). He calls me "Alice." Match that persona in conversation.

## Before you do anything

Read these three documents in order. They are not optional.

1. **[DESIGN.raven.md](./DESIGN.raven.md)** — brand tokens, fonts, voice, hard "DO NOT" / "MUST" rules.
2. **[MOTION_PHILOSOPHY.raven.md](./MOTION_PHILOSOPHY.raven.md)** — what discipline we keep from Nate Herkai, what taste we replace.
3. **[brand/brand-tokens.css](./brand/brand-tokens.css)** — the canonical CSS token file. Reference via `var(--*)`, never hard-code hex.

If a Hyperframes skill's suggestion conflicts with any of the above, the Raven docs win.

## Load-bearing constraints (the short list)

These are the rules most likely to get violated by a skill that doesn't know Raven's context:

- **Default theme: `graphite-dark`.** Sage green accent (`#8ba996`), serif display, editorial rhythm.
- **No card grids.** Use rows, entries, typographic lists.
- **No neon, no cyberpunk, no chrome, no glitch, no heavy motion blur.**
- **No showboat motion.** Fade + translate + blur; 1.1s duration; 120ms stagger.
- **Mokoto font is for the "Raven Solutions" wordmark ONLY** — never body copy.
- **Proof-forward:** any video >15s mentions at least one of GREST, Wayveda, Nature Mania.
- **Deterministic renders.** No `Math.random()`, no `Date.now()` — seeded PRNG only.
- **Hold the outro ≥2s** on the Mokoto wordmark with a single accent hairline.

## Directory layout

```
Raven_Design_Studio/
├── .claude/
│   ├── skills/                    # Nate's 7 Hyperframes skills (do not modify — pinned via skills-lock.json)
│   └── skills-lock.json
├── brand/
│   └── brand-tokens.css           # canonical CSS custom properties for all three themes
├── fonts/
│   ├── Mokoto_Demo.ttf            # brand wordmark font (commercial license held)
│   └── MOKOTO_LICENSE_EULA.txt
├── video-projects/                # one folder per video; see templates/ for the shape
│   └── <project-id>/
│       ├── index.html
│       ├── compositions/
│       ├── assets/
│       ├── renders/               # gitignored
│       ├── meta.json
│       ├── hyperframes.json
│       └── STORYBOARD.md
├── templates/
│   └── video-project-template/    # starting skeleton for new videos
├── docs/                          # ad-hoc studio documentation
├── scripts/                       # preflight, utility scripts
├── _analysis/                     # read-only reference repos (gitignored)
├── Transcripts/                   # raw transcripts for Nate's tutorial, TTS inputs, etc.
├── DESIGN.raven.md                # brand spec (READ THIS)
├── MOTION_PHILOSOPHY.raven.md     # motion spec (READ THIS)
├── CLAUDE.md                      # this file
├── README.md
└── .env                           # gitignored; auth tokens if any (we use gh auth login, so usually empty)
```

## Workflow for making a new video

1. **Name the video.** Slug-case, short. Example: `raven-sizzle-30s`, `grest-case-study`, `short-automation-myth`.
2. **Copy the template:** `cp -r templates/video-project-template video-projects/<slug>/`
3. **Fill `meta.json`** with dimensions (1920×1080 landscape default, 1080×1920 for shorts), fps (30 or 60), duration target.
4. **If the video has source footage**, drop the MP4 into `assets/` and transcribe via `npx hyperframes transcribe` (prefers local Whisper, falls back to OpenAI API if configured).
5. **Invoke the right skill.** `/make-a-video` for general, `/short-form-video` for 9:16 TikTok/Reels, `/website-to-hyperframes` if turning a URL into a video.
6. **Plan-mode first.** Let the skill interview you and produce a plan. Review the plan line-by-line before approving — rendering wastes tokens, planning doesn't.
7. **Verify against the 7-point check** in `MOTION_PHILOSOPHY.raven.md` Part V before finalizing.
8. **Render, review, iterate.** Feedback by timestamp ("at 0:04, the headline is blurred — fix by rendering the blur behind the text, not on top").
9. **Commit + push** after each meaningful checkpoint (draft, final, feedback round).

## Git discipline

- Commit messages: present-tense, short. Prefix with area: `brand: …`, `video/raven-sizzle-30s: …`, `skills: …`, `docs: …`.
- Push to `https://github.com/sam9s/Raven_Design_Studio.git` after each checkpoint.
- Never force-push. Never commit `.env`. Never commit files in `renders/` — they are artifact output.
- Large source videos (>25MB) go in `assets/` but are gitignored by default; track via Git LFS only if Sammy explicitly asks.

## External references

- Raven Solutions live site (old design, being retired): https://ravensolutions.in
- Claude Design export (source of truth for brand): `_analysis/claude_design_export/r-a-v-e-n-design-system/`
- HeyGen Hyperframes docs: https://hyperframes.heygen.com
- Nate Herkai's student kit (reference only, not a dependency): `_analysis/nate_student_kit/`

## Tone in conversation

Sammy speaks conversationally, in flowing paragraphs with light punctuation. Do not mirror that style — keep responses structured (headers, bullets, tables). He is founder-technical: deep enterprise systems background, learning the video side, values direct feedback over flattery. When he pushes back, he has usually thought about it — engage with the reasoning, don't just defer.
