# STORYBOARD — Raven Solutions 30s Sizzle

**Job.** Introduce Raven Solutions to a founder or operations lead at an Indian SME who has never heard of us, in under 30 seconds, and leave them with one concrete reason to believe we execute real work — not another AI pitch.

**Audience.** Founders / COOs / ops leads at 50–500-person businesses who deal with Shopify, CRM, warehouse, and customer-support tool sprawl every day.

**End state.** Viewer thinks: *"These people actually do the work. Not another dashboard."*

**Call to action (implicit, not overt).** The Mokoto wordmark is the memory hook. No button-press copy. A sizzle is a calling card, not a landing page.

**Format.** Silent with music bed. On-screen text only. Landscape 1920×1080, 30fps, 30s.

---

## 1. Theme, palette, and texture

- `data-theme="graphite-dark"` throughout.
- Accent: `#8ba996` (sage green).
- Background: token gradient + the 92px grid at 14% opacity.
- Atmosphere gradient drifts slowly in the top-left corner for the full 30s.
- Typography: DM Serif Display for headlines; Plus Jakarta Sans for eyebrows/subtitles; Mokoto for the outro wordmark only.

---

## 2. The nine beats

Total runtime 30.0s. Slowest beat 4s, fastest 2s, average 3.3s. Matches Raven's editorial pace (Sammy's "not too fast" adjustment from the website redesign).

| # | Timecode | Duration | Beat | Primary element | Motion primitive | Copy on screen |
|---|---|---|---|---|---|---|
| 1 | 0:00–0:02 | 2.0s | **Establish.** Grid texture fades up from 0 → 14%. Atmosphere gradient begins drift. | Eyebrow in top-left: `RAVEN SOLUTIONS · 2026` with hairline rule growing 0 → 32px beside it. | Grid fade-in; hairline sweep; eyebrow reveal | `RAVEN SOLUTIONS · 2026` |
| 2 | 0:02–0:05 | 3.0s | **Thesis headline.** Centre-left, DM Serif Display, 4rem. | Typewriter reveal, 22ms per character, into final state. | Typewriter | `Automation that executes real business work.` |
| 3 | 0:05–0:08 | 3.0s | **Counterpoint subtitle.** Below the headline, Plus Jakarta Sans 500, muted text color, max-width 42rem. | Reveal (opacity + 22px Y-translate + 4px blur → 0, 1.1s ease). | Reveal | `Not dashboards. Not demos. Execution.` |
| 4 | 0:08–0:11 | 3.0s | **Services strip.** Four monospace-feel pills in a single row at bottom third. Border, accent letter, no fill. | Push slide in from below (8%), staggered 120ms left-to-right. Outgoing beats 2+3 push up 8% and fade. | Push slide + stagger | `Process Automation · AI Chatbots · Internal Tools · Integrations` |
| 5 | 0:11–0:15 | 4.0s | **Proof 1 — GREST.** Left column: `i.` index (serif italic, muted) + client name `GREST` in DM Serif Display 3rem. Right column: stat cluster with hairline divider. | Reveal on left column; number-tick on the "5" count-up in right column. | Reveal + number tick | `GREST`<br>`Refurbished electronics · Ops, Sales, CX`<br>`5 projects · 4 delivered, 1 ongoing` |
| 6 | 0:15–0:19 | 4.0s | **Proof 2 — Wayveda.** Same structure as beat 5 but with `ii.` index. Tagline is quoted line. | Blur crossfade from beat 5 (500ms). Reveal on client name + description. | Blur crossfade + reveal | `WAYVEDA`<br>`Shopify × Shiprocket reconciliation`<br>`Closed a workflow other vendors could not.` |
| 7 | 0:19–0:23 | 4.0s | **Proof 3 — Nature Mania.** Same structure. Multi-courier names as muted inline list. | Blur crossfade + reveal. | Blur crossfade + reveal | `NATURE MANIA`<br>`250+ orders / day · Delhivery · Xpressbees · Ekart · DTDC`<br>`Delivered in < 48 hours.` |
| 8 | 0:23–0:26 | 3.0s | **Closing line.** Centre, DM Serif Display. The accent color only appears on one word: "simplify." | Kerning collapse (letter-spacing 0.4em → -0.01em over 1.2s). | Kerning collapse | `Let's simplify how your business operates.` |
| 9 | 0:26–0:30 | 4.0s | **Outro hold.** Mokoto wordmark `Raven Solutions` centre, 5rem. Accent hairline beneath (320px wide, 1.5px tall) sweeps in. Absolute stillness for final 2.5s. | Reveal (wordmark, 1.1s) + hairline sweep (beneath, 800ms) + **hold ≥2s**. | Reveal + hairline + hold | `Raven Solutions` |

---

## 3. Proof touchpoints — explicit mapping

Chat transcript rule: "Indian SMEs trust proof more than promise." Every proof reference uses **real copy from the shipped `siteContent.ts` copy deck**, not paraphrases. Source verified against `_analysis/claude_design_export/.../project/content/siteContent.ts`.

- **0:11–0:15** — GREST (grest.in) — *Refurbished Electronics · Ops/Sales/CX · 5 projects, 4 delivered, 1 ongoing*
- **0:15–0:19** — Wayveda (wayveda.com) — *Shopify × Shiprocket delivered-order reconciliation — "solved a workflow other vendors had not been able to close cleanly"*
- **0:19–0:23** — Nature Mania (naturemania.in) — *250+ daily orders · multi-courier visibility · delivered in < 48 hours*

Three proof beats consume 12 of 30 seconds (40%). That density is intentional — the sizzle is 40% proof, 40% thesis, 20% brand frame.

---

## 4. Audio direction (for future scoring pass — not rendered in V1)

- **Genre.** Editorial / documentary score. Think Aaron Copland sparseness + restrained synth pad + soft piano.
- **NOT.** EDM, drum drops, upbeat corporate rock, trap-inspired 808s, hype cues.
- **Key sonic moments:**
  - 0:02 — first light piano note on headline typewriter start.
  - 0:11 — low bass pad enters with GREST reveal; sustains through all three proofs.
  - 0:23 — pad hold, everything else strips away for the closing line.
  - 0:26 — single resonant note on wordmark reveal, decays over outro hold.
- **Music bed goes in `assets/music.wav`** once chosen. Royalty-free sources: Epidemic Sound, Musicbed, Artlist. V1 will render silent; music layered in V2.

---

## 5. Outro specification (must pass pre-render check)

- Mokoto wordmark on `#151716` graphite-dark background.
- Font-size 5rem, letter-spacing 0.06em, color `var(--text-primary)` (#f1ede5).
- Accent hairline directly beneath: 320px wide × 1.5px tall, color `var(--accent)` (#8ba996), sweeps in from left to right over 800ms.
- Wordmark fades in via reveal primitive (opacity + 22px Y-translate + 4px blur → 0, 1.1s).
- **Hold from 0:28.2 to 0:30.0 — no motion of any element.** The grid shimmer and atmosphere drift continue subliminally.

---

## 6. Pre-render 7-point check (to be verified before final)

Per `MOTION_PHILOSOPHY.raven.md` Part V:

- [ ] Every transition has motion (no raw cuts). — **Planned:** typewriter, reveals, push-slide, blur crossfades, kerning collapse. ✓
- [ ] Slowest beat ≥1.1s; every scene ≥1.5s. — **Planned:** shortest beat is 2.0s, most are 3–4s. ✓
- [ ] All colors via CSS tokens, not hex. — **Planned:** index.html will import `brand-tokens.css` and reference only `var(--*)`. ✓
- [ ] 92px grid visible at 14% throughout. — **Planned:** body::before from tokens file. ✓
- [ ] Outro holds wordmark ≥2s with hairline rule. — **Planned:** 0:28.2–0:30.0 = 1.8s hold (slightly tight — may extend wordmark reveal earlier or shorten beat 8 by 200ms to get true 2s hold). **FLAG for final tuning.**
- [ ] ≥1 real proof reference if >15s. — **Planned:** three of them at 0:11–0:23. ✓
- [ ] Passes "serious technical document that respects the reader" smell test. — **To be judged at preview stage.**

---

## 7. Open questions for Sammy

1. **Music now or later?** I've scoped this as a V1 silent render with music layered in V2. If you want music in V1, send a track suggestion or describe the feel in one sentence and I'll source.
2. **Real client URLs on screen?** The chat transcript showed you left this unresolved for the website. My default here is: show `grest.in`, `wayveda.com`, `naturemania.in` in small muted text beneath each client name. Ack if that's fine; say "no URLs" if not.
3. **End card CTA line?** I have left the outro as wordmark-only — no "Visit us at" or "DM us." That matches the "restrained, editorial" direction. If you want a contact line (email / phone / "ravensolutions.in") to flash at 0:29, say the word.
4. **The word "simplify" highlighted in accent color** — beat 8. If you'd rather no word-level accent (pure monochrome headline), say so.
5. **Outro hold duration.** My planned hold is 1.8s; the pre-render check mandates ≥2s. I propose extending beat 9 to 4.2s by shortening beat 7 (Nature Mania) from 4.0s to 3.8s. Minor change, preserves rhythm. OK?

---

## 8. What I'll do once you approve the storyboard

1. Build the composition HTML + GSAP timeline in `index.html` + `compositions/` — one file per major scene section for modularity.
2. Wire everything to `brand-tokens.css` with zero hard-coded colors.
3. Run `npx hyperframes lint` and `npx hyperframes validate`.
4. Preview locally at `localhost:3002`.
5. Sample three frames for sanity check (0:05, 0:15, 0:28).
6. If it looks right, full render to `renders/v1.mp4`, then show you the MP4 for feedback.
7. Iterate by timecode per your feedback (Nate-style loop).
