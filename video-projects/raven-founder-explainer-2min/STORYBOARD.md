# STORYBOARD — Raven Solutions Founder Explainer (2 min)

**Job.** In ~2 minutes, introduce Samret "Sammy" Singh as the founder of Raven Solutions to a stranger who lands on the company's YouTube — and make that stranger think "I want to talk to him about our workflow problem."

**Audience.** Founders / COOs / ops leads at Indian SMEs, 50–500 employees, who found the Raven YouTube channel via search or referral.

**Format.** 1920×1080 landscape, 30 fps, target 120s. **No face-cam.** Voiceover + Raven motion graphics + real GREST IMS screen recordings.

**Voice.** Sammy's own, recorded as audio-only. Script draft is at `SCRIPT.md`.

**What makes it work:** the screen recordings of GREST IMS. Talking about building an ERP is one thing; watching a working dashboard populate with live data is another. The proof is the product operating.

---

## Visual spine

Same brand language as the 30s sizzle. Graphite-dark default. DM Serif Display + Plus Jakarta Sans + Mokoto for the outro. Sage accent. 92px grid texture. Editorial motion — reveals, count-ups, hairline sweeps. No neon, no glitch, no showboat.

**New capabilities this format introduces:**
- Karaoke-style captions synced to voiceover words (via Whisper transcription).
- Screen-recording clips as inline visual anchors.
- Longer pacing — beats can breathe for 10–15 seconds each.
- One optional founder-photo card (LinkedIn-quality headshot). Skip if Sammy prefers.

---

## Beat structure (synced to script)

Every beat pairs a **narration segment** (from `SCRIPT.md`) with a **visual anchor**. Timecodes are approximate — final timing comes from Whisper transcription of Sammy's actual recording.

| # | Script section | Timecode | Visual anchor | Motion |
|---|---|---|---|---|
| 1 | HOOK | 0:00–0:12 | Graphite canvas + grid fades up. Accent rule sweeps in. Karaoke caption appears in centre-low. Optional "founder photo" fades in small on the right at 0:06 (skip if Sammy opts out). | Grid fade, caption reveal, hairline sweep |
| 2 | WHO I AM | 0:12–0:30 | Mokoto "Raven Solutions" wordmark fades into the frame centre-left; subtitle beneath: "Samret Singh · Founder" (in DM Serif Display). Caption stays low-centre. | Reveal + kerning collapse on the wordmark |
| 3 | WHY RAVEN EXISTS | 0:30–0:58 | Three principle cards appear in stagger as he speaks: "Execute real work" · "Not another dashboard" · "Practical automation." Each is a Ledger-style row (hairline divider), no card chrome. | Row stagger reveal |
| 4 | GREST — thesis | 1:00–1:15 | **Screen recording #1** (`dashboard-landing.mp4`) plays inside a browser frame similar to the sizzle's Wayveda treatment. URL bar shows `wh.sam9scloud.in/ims/dashboard`. | Browser scale-in, then clip plays with cursor |
| 5 | GREST — roadmap | 1:15–1:35 | **Screen recording #2** (`sidebar-navigation.mp4`) cuts in showing module hover states. Below the browser: same roadmap strip from the sizzle (Phase 1 IMS UAT · Phase 2 D2C · Phase 3 B2C · Phase 4 B2B) fades in beneath the clip, synced to "every channel, one module at a time." | Clip + roadmap reveal |
| 6 | GREST — building alongside | 1:35–1:45 | **Screen recording #3** (`a-real-workflow.mp4`) plays. | Clip continues; caption syncs |
| 7 | WAYVEDA + NATURE MANIA | 1:45–2:00 | Switch to warm-editorial cream theme (like sizzle's Nature Mania beat). Two side-by-side proof cards: Wayveda on left (Shopify × Shiprocket, "<48h"), Nature Mania on right (250+/day, 4 couriers, "<48h"). | Palette flip, card reveals |
| 8 | CLOSE | 2:00–2:10 | Back to graphite-dark. Mokoto "Raven Solutions" wordmark centre, accent hairline, tagline "Founder-led · Direct · Practical" (or similar restraint-per-brand). **Screen recording #4** (`theme-switcher.mp4`) plays very briefly (~3s) in the lower-right corner as a micro-anchor, then fades. | Reveal + hold |
| 9 | CONTACT HOLD | 2:10–2:15 | Hold on wordmark with a quiet contact line beneath: `sammy@ravensolutions.in · ravensolutions.in`. Hairline stays lit. | Static hold |

Total approximate runtime: **2:15**. Final comes out whatever the transcribed audio is.

---

## Caption treatment (karaoke)

- Centre-low placement (bottom third, above the motion graphics).
- Font: Plus Jakarta Sans, 34px, weight 500.
- Current word highlighted in sage (`var(--accent)`); rest in `var(--text-primary)`.
- Background: none — subtle 6px blur drop behind the caption container to maintain legibility over any scene.
- Syncs to Whisper word-level timestamps; no manual timing.

## Founder photo (optional)

If Sammy provides a square LinkedIn-quality headshot:
- Appears ONCE, at ~0:06–0:14 (during the hook → who-I-am transition).
- Placement: right third of frame, ~180×180px, circular crop, sage accent ring (1.5px), subtle drop shadow.
- Fades out when the wordmark becomes the hero.

If Sammy prefers no photo at all: the wordmark becomes the hero from 0:06 onward. Zero loss of polish.

## Audio layers

1. **Voiceover** — Sammy's recording. Primary track. Volume 1.0.
2. **Music bed** — optional ambient/piano background at ~0.20 volume so the VO stays intelligible. We can use the same LightBeats track or a calmer one; Sammy's choice. TBD after VO lands.
3. **UI micro-sounds** — optional. Single soft tick when each principle-card lands. Skip unless explicitly wanted.

## Open questions for Sammy

1. **Founder photo — yes or no?** Default no unless he says otherwise.
2. **Music bed under voiceover — yes, no, or picked later?** Default: picked later, after hearing VO alone at V1.
3. **End-card CTA — just email + URL, or also a phone number?** Your call.

## What's next

1. **Sammy reads & rewrites `SCRIPT.md` in his own voice.** Takes ~20–30 minutes.
2. **Sammy records voiceover** (reading the final script, 2–3 takes of the full thing). Saves to `assets/voiceover.mp3` or `.wav`.
3. **Sammy records 4 screen clips** per `SCREEN_RECORDING_GUIDE.md`. Saves to `assets/screen-recordings/`.
4. **Sammy says "ready."**
5. I transcribe VO via Whisper → get word-level timestamps → compose timeline → render V1.
