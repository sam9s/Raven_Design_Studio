# STORYBOARD — Raven Solutions 30s Sizzle (V2)

**Job.** Introduce Raven Solutions to a founder or operations lead at an Indian SME who has never heard of us, in under 30 seconds, and leave them with one concrete reason to believe we execute real work — not another AI pitch.

**Audience.** Founders / COOs / ops leads at 50–500-person businesses who deal with Shopify, CRM, warehouse, and customer-support tool sprawl every day.

**End state.** Viewer thinks: *"These people actually do the work. Not another dashboard."*

**Call to action (implicit, not overt).** The Mokoto wordmark is the memory hook. No button-press copy. A sizzle is a calling card, not a landing page.

**Format.** Silent with music bed planned for V2 layering. On-screen text only. Landscape 1920×1080, 30fps, 30s.

**What changed from V1.** V1 was nine typographic beats — reveals, kerning collapses, hairline sweeps. Technically on-brand for "editorial restraint" but lacking the motion density that makes Nate Herkai's sizzles feel professionally produced. Sammy's (correct) feedback: "simple, blatant, and totally unattractive." V2 drops thesis/services explicit beats. The proofs *are* the thesis. Three clients, three different visual techniques, one outro. Registry-inspired but custom-authored in Raven tokens (registry blocks themselves are not drop-in — they hardcode Inter/Libre Baskerville/Figma palette).

---

## 1. Theme, palette, and texture

- `data-theme="graphite-dark"` throughout.
- Accent: `#8ba996` (sage green).
- Background: token gradient + the 92px grid at 14% opacity.
- Typography: DM Serif Display for headlines; Plus Jakarta Sans for body; Mokoto for the outro wordmark only; **JetBrains Mono for the terminal beat only** (terminal is the single exception to the two-font rule — it reads as "code," and code is typed in mono).

---

## 2. The five beats

Total runtime 30.0s. Three 7-second proof beats with Nate-pace density, framed by a 3s cold open and a 6s outro.

| # | Timecode | Duration | Beat | Visual technique | Motion primitives |
|---|---|---|---|---|---|
| 1 | 0:00–0:03 | 3.0s | **Cold open — terminal.** `$ raven execute order-reconciliation` types character-by-character with blinking sage cursor, then a result line appears: `→ matched 1,428 / 1,432 orders · 97% confirmed`. | Inspired by Nate's `v00-cold-open` pattern, authored fresh in Raven mono. | Character stagger type-on (30ms), cursor blink (CSS), result reveal (1.0s). |
| 2 | 0:03–0:10 | 7.0s | **GREST dossier.** Header `i. GREST` + subline. Five numbered project rows reveal top-to-bottom with hairline dividers between each: AI Chatbot (✓), Cart Recovery (✓), TeleCRM Auto (✓), Warehouse Mgmt (✓), D2C Fulfilment (● Ongoing). | Flowchart-like stagger pattern, reframed as a Ledger-style dossier (no cards). | Header reveal, subline reveal, row stagger with x-slide + blur (320ms per row). |
| 3 | 0:10–0:17 | 7.0s | **Wayveda reconciliation.** Left column: name + description + pull-quote with accent rule. Right column: `1,432` Shopify orders → `1,428` Shiprocket matched → `✓ Reconciled`. Numbers count up; arrow draws; reconciled stamp lands. | `macos-notification` data density + `data-chart` count-up motion — hybrid. | Reveal + number tick + arrow draw + stamp entrance. |
| 4 | 0:17–0:24 | 7.0s | **Nature Mania courier split.** Header row with name + `250+` stat (count-up). Four horizontal bars draw in stagger with sage accent fill: Delhivery 42%, Xpressbees 28%, Ekart 18%, DTDC 12%. | `data-chart` bar-stagger motion in Raven palette. | Number tick (stat) + width tween per bar + label fades. |
| 5 | 0:24–0:30 | 6.0s | **Outro hold.** Previous beat blur-crossfades. Mokoto wordmark reveals (1.2s). Accent hairline sweeps beneath (900ms). Tagline "Automation that executes" fades in (700ms). Absolute stillness for final 3s. | Registry `logo-outro` reveal technique, Mokoto wordmark is our logo (no SVG re-authoring). | Reveal primitive + hairline sweep + delayed tagline + hold. |

---

## 3. Proof touchpoints — explicit mapping

All three clients from the shipped `siteContent.ts` copy deck. Every number is real.

- **0:03–0:10** — GREST (grest.in) · 5 projects (4 delivered + 1 ongoing)
- **0:10–0:17** — Wayveda (wayveda.com) · 1,428 / 1,432 orders reconciled · quote from siteContent.ts verbatim
- **0:17–0:24** — Nature Mania (naturemania.in) · 250+ orders/day across 4 couriers, delivered <48h

**Proof density:** 21 of 30 seconds (70%) are proof beats. The cold open previews the proof theme (order reconciliation). The outro is pure brand. Zero seconds of explicit "we do X, Y, Z" thesis copy — the proofs *are* the thesis.

---

## 4. Outro specification (passes pre-render check)

- Mokoto wordmark "Raven Solutions" centred, 196px, letter-spacing 0.06em, color `var(--text-primary)`.
- Accent hairline beneath: 420px wide × 1.5px tall, color `var(--accent)`, sweeps in from 0 → full width over 900ms.
- Small tagline beneath the rule: "Automation that executes" — Plus Jakarta Sans 20px, 600 weight, 0.24em letter-spacing, `var(--text-muted)` color.
- **Hold from 0:27.0 to 0:30.0 = 3.0s absolute stillness.** ≥2s requirement ✓.

---

## 5. Pre-render 7-point check

Per `MOTION_PHILOSOPHY.raven.md` Part V:

- [x] Every transition has motion (blur crossfade between beats; no raw cuts).
- [x] Slowest active beat ≥1.1s; every scene ≥3s.
- [x] All colors via CSS tokens, not hex — every color references `var(--*)`.
- [x] 92px grid visible at 14% throughout (body::before token).
- [x] Outro holds wordmark ≥2s with hairline rule — 3.0s hold.
- [x] ≥1 real proof reference if >15s — three real proofs, 70% of runtime.
- [x] Passes "serious technical document that respects the reader" smell test — no hype copy, no showboat motion, Ledger-style dossier for GREST, editorial count-ups for metrics.

---

## 6. What we deferred

- **Music bed.** V1 silent. Once V2 renders cleanly and looks right, Sammy picks one track via the acoustic brief in this doc's appendix (see Appendix A). We then mux with ffmpeg in V3.
- **Shader transition.** Proposed `light-leak` shader between Nature Mania and outro; deferred because the registry shader blocks are not drop-in (they hardcode Figma-themed scaffold). Simple blur crossfade serves the rhythm adequately for V2.
- **GREST logo / Wayveda logo / Nature Mania logo.** Not included on screen — names alone are cleaner at 30s. Logos would pull visual weight away from the numbers.

---

## Appendix A — Acoustic brief for V3 (music layering)

Direction B — "Quiet Momentum." Slow-tempo (~80 BPM) editorial score. Arpeggio piano + low pad + felt pulse (no drum kit). Gentle forward motion without urgency. Reference feel: Ludovico Einaudi "Experience," Nils Frahm piano ambient.

Arc:
- 0:00 — sparse piano enters with terminal type-on.
- 0:03 — low pad layer joins at GREST dossier start; sustains through Wayveda + Nature Mania.
- 0:23 — strip to pad alone entering outro.
- 0:24 — single resonant piano note on Mokoto wordmark reveal; decays through hold.

Pixabay search: `inspirational piano ambient`, `documentary piano emotional`, `cinematic piano slow`.

Destination: `assets/music.mp3` or `.wav`.
