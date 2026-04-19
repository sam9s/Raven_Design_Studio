# MOTION_PHILOSOPHY.raven.md

How Raven Design Studio videos should move. This document is a fork of Nate Herkai's `MOTION_PHILOSOPHY.md` (the Hyperframes student kit) — we keep the **engineering discipline**, we reject the **visual taste**. Our aesthetic is editorial, restrained, quiet authority. Nate's reference is kinetic, neon, chrome-halo. They are opposites.

Read this **after** `DESIGN.raven.md`, **before** invoking any video skill.

---

## Part I — What we inherit from Nate (keep)

These are framework-level rules. They are not aesthetic — they are how Hyperframes videos avoid looking cheap and broken.

1. **One idea per beat. Cut fast, average ~1.5–2s per scene** for marketing/ad videos. Longer holds are reserved for the outro and hero shots.
2. **Timelines must fill their slots.** Every GSAP timeline ends with `tl.to({}, { duration: SLOT_DURATION }, 0)` — no black-frame flashes.
3. **Motion in every transition.** Cuts feel cheap; a transition (blur crossfade, wipe, push, or fade) feels intentional. Even a 200ms overlap reads as deliberate.
4. **Deterministic renders.** Never `Math.random()`, never `Date.now()`, never `performance.now()` inside a composition — all randomness must come from a seeded PRNG derived from frame index. Otherwise renders will not match between preview and final pass.
5. **Camera never sleeps.** Even "still" frames breathe — grid drift, vignette pulse, atmosphere gradient drift. Absolute stillness reads as a frozen PDF, not a video.
6. **Hold the hero.** Logo reveal ≥2s at the end. Outro cards get weight, not a quick flash.
7. **Type is a character.** Words are never filler — they scale, morph, collapse, reveal with purpose. But (Raven override) always editorially, never kinetically.
8. **Audio is a feature, not decoration.** Music is a timing track. Captions sync to word-level timestamps. Use Whisper transcription locally or via OpenAI API when available.

## Part II — Where we diverge from Nate (replace wholesale)

Nate's default aesthetic comes from the "Infinite — Global Payments" 30s spot he analyzes in his MOTION_PHILOSOPHY. Raven is not that brand. We replace taste while keeping discipline.

| Dimension | Nate's default ("Infinite") | Raven's replacement |
|---|---|---|
| Canvas | ~90% black (`#000`) | `graphite-dark` (`#151716`) OR `warm-editorial` (`#fafaf7`) — never pure black |
| Texture | Perspective grid + crosshair registration marks | 92px subtle grid at 14% opacity |
| Accent strategy | Chrome gradients, neon halos, light beams | Single restrained accent per theme (sage / forest / teal-navy) |
| Typography | Kinetic type, 8× scale, morph, glow | DM Serif Display, `-0.01em` tracking, never glows |
| Transitions | Whip-pans, shader vortices, chromatic splits, thermal distortion | Blur crossfade (4px → 0), 22px Y-translate, fade (1.1s) |
| Stagger | Aggressive 40–80ms | Slower, 120ms — matches Sammy's pacing feedback |
| Camera moves | 3D tilts, parallax depth, rubber-band easing | Flat plane. Gentle atmospheric gradient drift only |
| Object metaphors | Recurring hero object (coin/card) with motion blur streaks | Recurring wordmark + hairline rule — no streaks |
| Outro | Logo hold with halo bloom | Mokoto wordmark on graphite, accent hairline beneath, absolute stillness |
| Color palette | Symbolic neon pairs | Restrained: one accent + 4 greys per theme |

## Part III — Raven's motion vocabulary (the only moves we use)

A composition should assemble from these primitives. If a move isn't here, propose it before using it.

### Entrance primitives
- **Reveal.** Opacity 0→1 + `translateY(22px → 0)` + `blur(4px → 0)`. Duration 1.1s. Ease `cubic-bezier(0.16, 1, 0.3, 1)`. This is the default — used 70% of the time.
- **Typewriter.** Character-by-character reveal for headlines, 22ms per character. Use once per composition, at most.
- **Kerning collapse.** Hero headline starts at `letter-spacing: 0.6em`, collapses to `-0.01em` over 1.3s. Used for the final hero only.
- **Hairline sweep.** 1–2px accent-colored rule grows from 0 → 32–40px, 800ms, ease-out. Paired with every eyebrow label entrance.
- **Number tick.** Stat values count up from 0 to target over 800ms, monospace-aligned.

### Transition primitives
- **Blur crossfade.** Outgoing element blurs to 4px and fades; incoming reverses. 500ms overlap.
- **Push slide.** Outgoing translates up 8%, incoming enters from below 8%. 650ms. Used when the subject changes but the tone doesn't.
- **Hold.** Sometimes the best transition is no transition — 300ms absolute stillness before the next beat.

### Ambient primitives
- **Atmosphere drift.** The radial gradient in the top-left corner drifts by ±2% of frame width over 12s. Constant, subliminal.
- **Grid shimmer.** The 92px grid opacity breathes between 12% and 16% over 8s. Unnoticeable consciously; felt subliminally.

### Explicitly banned primitives
- Rubber-band / elastic easing.
- Overshoot / back-easing on any element.
- 3D rotation (`rotateX`, `rotateY`, `rotateZ` > 5deg).
- Heavy motion blur streaks (Nate's "whip streak" is banned).
- Particle systems of any kind.
- Shader vortices, chromatic splits, thermal distortion (from the Hyperframes shader registry).
- Neon glow (`text-shadow: 0 0 N var(--accent)` with N > 4px).
- Scale > 1.15× on any element.

## Part IV — Timing discipline

Sammy explicitly flagged pacing as a problem during the website redesign: *"on the other pages the animation is much gradual and slower… it's too fast while scrolling I am not even feeling it."* The lesson for video is the same — we run **slower than Nate**.

- Default reveal: **1.1s** (Nate's default: 0.7s)
- Default stagger: **120ms** (Nate's default: 60ms)
- Default transition: **650ms** (Nate's default: 400ms)
- Hero hold: **≥2s** (matches Nate)
- Outro card: **≥3s** (Nate: 5s+ — we're a touch shorter but still unhurried)

## Part V — The seven-point pre-render check

Before approving any render for distribution, every composition must pass all seven:

1. Does every transition have motion (no raw cuts)?
2. Is the slowest beat ≥1.1s and is every scene ≥1.5s?
3. Are all colors referenced via CSS tokens, not hex?
4. Is the grid texture visible at 14% opacity on every frame (unless intentionally excluded)?
5. Does the outro hold the wordmark ≥2s with a hairline rule?
6. Is there at least one real proof reference (GREST / Wayveda / Nature Mania) if duration > 15s?
7. Would Sammy describe this as "a serious technical document that respects the reader" — or as "marketing hype"?

If any answer is "no," fix before rendering final.
