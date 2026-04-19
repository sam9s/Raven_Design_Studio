# Raven Design Studio

Internal AI-video-editing studio for **Raven Solutions**. Produces advertisement videos, shots, YouTube explainers, and short-form content — driven by Claude Code on top of HeyGen Hyperframes.

Owner: Samret "Sammy" Singh. Not for client delivery.

## Quick start

### Prerequisites
- Node.js 22+ and Bun (Hyperframes requires Bun for workspace ops; install from https://bun.sh).
- ffmpeg on PATH (`ffmpeg -version` should work).
- Optional: OpenAI API key (for Whisper transcription fallback) — add to `.env`.
- Optional: `whisper.cpp` for fully local transcription.

### First-time setup
```bash
# 1. Authenticate with GitHub (recommended over a raw PAT in .env)
gh auth login --with-token   # paste PAT when prompted, then Ctrl+D

# 2. Verify Hyperframes CLI works
npx hyperframes doctor

# 3. Read the brand docs (this step is not optional)
#    - DESIGN.raven.md
#    - MOTION_PHILOSOPHY.raven.md
#    - CLAUDE.md
```

### Make a new video
```bash
# Copy the template
cp -r templates/video-project-template video-projects/my-new-video

# Edit meta.json, drop source footage into assets/ if needed
# Then ask Claude Code:
#   /make-a-video         — general purpose
#   /short-form-video     — 9:16 vertical
#   /website-to-hyperframes  — turn a URL into a video

# Preview live in the browser
npx hyperframes preview video-projects/my-new-video

# Render to MP4
npx hyperframes render video-projects/my-new-video
```

## Repository shape

See `CLAUDE.md` for the full layout. In short:

| Path | What's inside |
|---|---|
| `DESIGN.raven.md` | Brand tokens, fonts, voice, hard rules. **Read first.** |
| `MOTION_PHILOSOPHY.raven.md` | Raven's motion discipline. Derived from Nate Herkai's framework, re-skinned with Raven's taste. |
| `brand/brand-tokens.css` | Canonical CSS custom properties for graphite-dark / warm-editorial / soft-slate themes. |
| `fonts/Mokoto_Demo.ttf` | Brand wordmark font (commercially licensed — for "Raven Solutions" only). |
| `.claude/skills/` | Hyperframes skills (copied from Nate's student kit, do not modify). |
| `templates/` | Starting skeleton for new video projects. |
| `video-projects/` | One folder per video. |
| `_analysis/` | Reference clones of HeyGen Hyperframes and Nate's student kit. Gitignored. |

## Why local, not VPS?

Rendering is CPU/RAM-bound and iteration happens through a local browser preview (`localhost:3002`). A typical VPS has fewer cores than a workstation and no GPU acceleration for Chrome's headless rendering. Shipping raw MP4 footage to a VPS every edit adds friction. Keep Raven's VPS free for what it's good at — client automation systems.

GitHub is the offsite backup. Commit often, push often.

## Credits

- Rendering engine: [HeyGen Hyperframes](https://github.com/heygen-com/hyperframes) (Apache 2.0)
- Workflow inspiration: [Nate Herkai's Hyperframes Student Kit](https://github.com/nateherkai/hyperframes-student-kit) (MIT, code only — brand assets are AIS property and are not used here)
- Design system: Claude Design (Anthropic) — the "R.A.V.E.N. Design System" export lives in `_analysis/` as reference.
