# DESIGN.raven.md — Raven Solutions visual identity for video

This is the canonical design document for every video, shot, ad, or asset produced inside `Raven_Design_Studio`. Read this before touching a composition. If a directive here conflicts with a Hyperframes skill's suggestion, **this document wins**.

Derived from the Claude Design handoff bundle (`_analysis/claude_design_export/r-a-v-e-n-design-system/`) — specifically the shipped React implementation (`project/index.css`, `project/content/siteContent.ts`) and the design-intent conversation (`chats/chat1.md`).

---

## 1. What Raven is

- **RAVEN** = Rapid Automation Virtual Engineers.
- An India-based automation practice delivering AI-assisted workflow systems to SMEs. Founder-led (Samret "Sammy" Singh). Live proof: GREST, Wayveda, Nature Mania.
- **This studio exists to produce media for Raven Solutions** — not for client deliverables. Advertisement shots, sizzle reels, YouTube explainers, social short-form, promo videos, internal launch films.

## 2. The chosen direction — "The Ledger"

Three directions were prototyped during the website redesign:

| Direction | Aesthetic | Status |
|---|---|---|
| **The Ledger** (graphite dark) | Engineering journal. Numbered sections. Monospace metadata. Proof as scrollable index. | **SELECTED — primary default** |
| **The Atelier** (warm cream) | Swiss / literary annual. Oversized serif hero, long scroll, pinned titles. | Available as `warm-editorial` theme — use sparingly |
| **The Control Room** (soft slate) | Financial-services premium. Asymmetric grid, composed density, quiet ticker. | Available as `soft-slate` theme — use sparingly |

Every video defaults to the Ledger aesthetic on the `graphite-dark` theme. Use `warm-editorial` only when the subject is long-form narrative (founder story, company vision, about-us). Use `soft-slate` only for technical case studies or whitepaper-style explainers.

## 3. The hard "DO NOT" list

Straight from Sammy's chat with Claude Design. These are not preferences — they are load-bearing rules.

1. **No card grids.** Use rows, entries, dossiers, typographic lists. "The card design is very generic and most AI-created websites have lots and lots of cards."
2. **No cyberpunk / neon / glitch.** That was the rejected original direction.
3. **No AI-generated feel.** This is the top-level acceptance test.
4. **No hype copy.** No "revolutionary," "magic," "unleash," "10x your…" Leave Sammy's verbatim copy alone.
5. **No showboat motion.** "Motion should reinforce reading, not showboat." Exclude: Apple-bounce, heavy parallax, 3D tilts, ribbon swipes, rubber-band easing.
6. **No `Math.random()` or `Date.now()` in compositions.** Hyperframes renders must be deterministic — seeded PRNG only.
7. **No card-stack 3D reveals borrowed from product demos.** Raven is a document, not an app.
8. **Do not replace Mokoto.** It's the wordmark. Do not apply it to body copy.

## 4. The hard "MUST" list

1. **Default theme is `graphite-dark`.** Explicit opt-in to switch.
2. **Proof-forward.** Every Raven video that runs longer than ~15 seconds must surface at least one real client reference (GREST, Wayveda, or Nature Mania) with a real outcome metric — before the final CTA.
3. **Editorial motion only.** Fade + translate + blur; typewriter reveals; kerning collapses; hairline underline sweeps. Duration 1.1s. Stagger 120ms.
4. **92px grid texture at 14% opacity** on every surface, unless the composition's subject demands a clean slate.
5. **Hold the outro.** Logo wordmark on black graphite, ≥2s, no motion, single hairline rule beneath.
6. **Copy tone:** calm, premium, founder-led, Indian-SME friendly. "Serious technical document that respects the reader."

## 5. Fonts

### Canonical stack (from shipped `index.css`)

| Role | Font | Notes |
|---|---|---|
| Brand wordmark only | **Mokoto** (`fonts/Mokoto_Demo.ttf`) | Load via `@font-face`. Used on the literal string "Raven Solutions" and nowhere else. Commercial license held by Sammy. |
| Display / headlines | **DM Serif Display** | Google Fonts. Weight 400. Letter-spacing `-0.01em`. |
| Body / UI | **Plus Jakarta Sans** | Google Fonts. Weight 400/500/600/700 as needed. |

### Alternate fonts (approved but not default)
The earlier prototype exploration used Fraunces / Newsreader / Inter / JetBrains Mono. These are sanctioned fallbacks if a specific video demands a different serif voice — but require explicit Sammy approval before use.

## 6. Color tokens (three themes)

Full token set lives in `brand/brand-tokens.css`. Quick reference:

### graphite-dark (DEFAULT)
```
bg-primary:    #151716   text-primary:    #f1ede5   accent:   #8ba996  (sage)
bg-secondary:  #1c1f1d   text-secondary:  #bdb7ad   border:   #2d322f
bg-dark:       #090a0a   text-muted:      #8e887f
```

### warm-editorial
```
bg-primary:    #fafaf7   text-primary:    #1a1a18   accent:   #2d4a3e  (deep forest)
bg-secondary:  #f4f2ed   text-secondary:  #6b6860   border:   #e3e0da
bg-dark:       #111110   text-muted:      #9c9a95
```

### soft-slate
```
bg-primary:    #f1f4f4   text-primary:    #18242a   accent:   #305f69  (teal-navy)
bg-secondary:  #e7ecec   text-secondary:  #596a71   border:   #d8e0e1
bg-dark:       #132025   text-muted:      #89979c
```

**Never hard-code hex values in compositions.** Always reference `var(--accent)`, `var(--text-primary)`, etc. This lets a single composition re-render under any theme.

## 7. Signature visual gestures

Every Raven video should use at least two of these — they are what make it recognizably Raven:

- **The 92px grid overlay** at 14% opacity over the entire frame.
- **Hairline accent rules** (1–2px tall, 32–40px wide, accent color) next to eyebrow labels.
- **Uppercase eyebrow labels** (0.72rem, 0.12em tracking, accent color) above every headline beat.
- **Numbered section indices** (i., ii., iii. — display serif, italic, muted color) for service and project listings.
- **Subtle atmosphere gradient** — a radial of `--atmosphere` (accent at low opacity) drifting slowly in the top-left corner.
- **Mokoto wordmark reveal** — always fades in from opacity 0 + 8px Y-translate, never scales, never glitches.

## 8. Copy decks (reuse verbatim)

The website's `siteContent.ts` contains finalized Sammy-approved copy. When a video needs a line about services, proof, or contact, pull from there rather than paraphrase. Key reusable fragments:

- **One-liner:** "Helping businesses automate routine work with AI and smart workflows."
- **Closing CTA:** "Let's simplify how your business operates."
- **Founder line:** "Founder & CTO at Raven Solutions | Building AI Agents for Business Automation | 18+ Years in Enterprise Systems & Automation"
- **Proof line:** "Raven Solutions has delivered workflow systems for businesses including GREST, Wayveda, and Nature Mania."

## 9. Checklist before rendering any video

- [ ] Default theme is `graphite-dark` unless the brief explicitly says otherwise.
- [ ] No card grid anywhere in the composition.
- [ ] At least one real proof reference (GREST / Wayveda / Nature Mania) if duration > 15s.
- [ ] Mokoto only on the "Raven Solutions" wordmark.
- [ ] 92px grid overlay present (unless subject demands clean slate).
- [ ] Motion durations are 1.1s with 120ms stagger (not Nate's 0.5s defaults).
- [ ] Copy passes the "calm, premium, Indian-SME friendly" smell test.
- [ ] Final frame: wordmark held ≥2s, accent hairline, no motion.
- [ ] Composition uses CSS custom properties, not hard-coded hex values.
- [ ] No `Math.random()` or `Date.now()` in any composition script.
