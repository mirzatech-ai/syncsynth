# SyncSynth — Monetization + Build Plan

**One engine, four revenue tracks.** SyncSynth = open-source `nw_wrld` modular sequencer + custom audio-reactive WebGL modules (the generative-shader kind just produced) → an automated visual-music content factory. Same core render pipeline feeds paid kits, ad-monetized streams, licensed loops, and commercial installs. Build once, sell four ways.

---

## 0. Core stack (build this first — everything else depends on it)

| Layer | What | Where |
|---|---|---|
| Sequencer core | `nw_wrld` forked, de-branded, privatized | `PROJECTS\SYNCSYNTH\core\` |
| Module library | WebGL/GLSL audio-reactive modules, theme-tagged | `PROJECTS\SYNCSYNTH\modules\` |
| Render farm | Headless Chromium + `puppeteer` → WebM/MP4 loop capture; `ffmpeg` for encode/tile/upscale | VPS worker or local batch |
| Audio bed | Royalty-free / self-generated stems (Suno-style or CC0 packs) — must own or clear every second used | `PROJECTS\SYNCSYNTH\audio\` |
| Publish rig | 24/7 RTMP loop pusher (`ffmpeg` → YouTube ingest), metadata/thumbnail pipeline | VPS `76.13.26.130` |

**Success gate for Phase 0:** one module renders a clean 60s seamless loop from an audio stem, headless, unattended, verified by an actual played-back screen-record — not "should render."

---

## Revenue Track 1 — Module Packs / VJ Kits (Gumroad + Etsy)

**Fastest cash, lowest lift.** Bundle code-generated premium modules by theme (e.g. "Neon Rain," "CRT Decay," "Liquid Chrome," "Brutalist Grid"). Sell as VJ-loop packs (MP4/HAP) + the raw module files for Resolume/nw_wrld users.

- **Agent role:** `KIMI` (code-class) generates + parameter-varies modules; `empire-crew` art-worker renders the loop previews and packages the ZIP; `KIN` writes the Gumroad/Etsy listing copy + pricing.
- **Free-fuel provider:** AiHubMix free tier (`coding-glm-5.1-free`) for module code generation; Cloudflare Workers AI / Groq for listing-copy + thumbnail-prompt drafting. Zero marginal LLM cost.
- **First-90-days:**
  1. Ship 3 themed packs (8–12 modules each) → Gumroad first (no listing fee, instant payout), mirror to Etsy for discovery.
  2. Price: $12–19 single pack, $39 "all-access" bundle. One free 2-module teaser pack as the funnel.
  3. Every pack MP4 preview = a YouTube Short (cross-feeds Track 2 subs).
  4. Target: first sale by day 14; $150–300/mo by day 90 with 5–6 packs live.

**Note:** Gumroad payout is direct — no new financial credential handling needed beyond Mo connecting his own account once, in his own dashboard.

---

## Revenue Track 2 — 24/7 YouTube Ambience Streams + Shorts (MAIN PAYOUT)

**The long-form engine.** 24/7 lofi / synthwave / deep-focus streams with unique reactive visuals + a steady Shorts drip. This is where watch-hours and the durable ad revenue live.

- **Agent role:** `MAYA` (COO) owns the channel calendar + retention analytics; `empire-crew` swarm runs the render→encode→upload pipeline; `Hermes` schedules the RTMP restarts and Short drops; `KIN` reviews titles/thumbnails against retention data weekly.
- **Free-fuel provider:** Gemini free tier for title/description/tag generation and thumbnail concepting; NVIDIA NIM / Groq for batch metadata; render is pure GPU/WebGL (no paid API). Cloudflare for the channel landing page.
- **First-90-days (path to Tier 1 = 500 subs + 3,000 watch-hrs + 3 uploads/90d):**
  1. **Weeks 1–2:** Launch 1 flagship 24/7 stream ("Synthwave Night Drive — Deep Focus"). A single unattended stream banks watch-hours around the clock — the fastest legitimate route to 3,000 hours.
  2. **Weeks 1–12:** 1 Short/day (auto-cut 20–40s reactive clips from the render farm). Shorts drive subscriber velocity toward 500.
  3. **Weeks 2–8:** Add 2 more themed streams (lofi study, ambient/drone sleep) — 3 distinct moods, distinct visual identities, cross-linked.
  4. **Retention loop:** `MAYA` pulls YouTube Analytics weekly; `KIN` reworks the bottom-quartile thumbnails/hooks. Loop until CTR and avg-view-duration climb.
  5. Realistic checkpoint: 500 subs + 3,000 hrs is achievable by day 90 with one always-on stream + daily Shorts if retention holds.

> **Payout nuance (don't misreport to Mo):** 500 subs + 3,000 hrs unlocks YPP *fan-funding* early access. Full *ad* revenue needs 1,000 subs + 4,000 hrs. Same content engine — Track 2 just keeps running past day 90 to clear the ad threshold. Flag, don't hide.

---

## Revenue Track 3 — Stock-Video Loops (Shutterstock / Pond5 / Adobe Stock)

**Passive back-catalog.** The same render farm outputs short seamless reactive loops (4–15s) licensed as stock motion backgrounds. One render → sold N times, forever.

- **Agent role:** `empire-crew` render + `KIMI` for the seamless-loop math; `KIN` handles the keyword/metadata sheet each platform demands (stock discovery is 90% metadata).
- **Free-fuel provider:** Groq / Gemini free tier for bulk keyword + title CSV generation per clip; render is GPU-native, no API cost.
- **First-90-days:**
  1. Pick the loop-friendly modules (abstract, non-branded, no third-party audio needed — stock loops are silent/visual).
  2. Batch-render 100 loops in 4K, tag with a CSV metadata pipeline.
  3. Submit to Pond5 first (best non-exclusive rev-share), then Adobe Stock, then Shutterstock. Non-exclusive across all three.
  4. Stock is a slow-burn — expect near-zero for 60 days, first trickle by day 90. Set it and let the catalog compound. Low attention cost = worth running in parallel.

**Note:** Each platform requires Mo to create/verify his own contributor account (identity + payout) — I set up the render/metadata pipeline; account creation and any tax/payout form is Mo's own action in his own dashboard.

---

## Revenue Track 4 — Live-VJ / Commercial Interactive Displays (Agency Service)

**Highest ticket, human-in-loop.** SyncSynth as a real-time, audio-reactive install engine for venues, brand activations, retail displays, event VJ sets. This is experiential-agency service revenue, not passive.

- **Agent role:** `KIN` scopes + quotes each gig; `KIMI`/`empire-crew` build the custom client module; `MAYA` runs the delivery checklist. Mo is the human closing the deal and running/attending the live set.
- **Free-fuel provider:** internal build only — AiHubMix free tier for the custom module code; no per-gig API cost, so margin is near-100% on labor.
- **First-90-days (foundation, not revenue yet — deals take a cycle):**
  1. Build one flagship interactive demo (mic/line-in → live visuals) hosted at a `syncsynth`-branded page behind the crawler-block `robots.txt`.
  2. Screen-record a 60s reel of it reacting live → becomes the sales asset + a YouTube Short (feeds Track 2).
  3. `KIN` drafts a one-page service sheet + tiered pricing ($300 event loop pack → $1,500+ custom live set → $5k+ install). Mo reviews before any outreach.
  4. Any outbound (cold email to venues/agencies) is drafted by `KIN` but **sent by Mo** — no messages go out on Mo's behalf without his explicit per-batch go.
  5. Target within 90d: demo reel live + 1 warm lead in conversation. Real close likely day 90–180.

---

## What makes ours NOT AI-slop (YouTube inauthentic-content survival)

YouTube's 2025+ policy demonetizes mass-produced, repetitive, low-effort content. SyncSynth passes because:

1. **A real generative engine, not a re-uploader.** Every visual is procedurally rendered from actual audio input through hand-built GLSL modules — no stock-image slideshows, no recycled clips. The pixels are genuinely ours and genuinely unique per render.
2. **Distinct, consistent brand aesthetic.** One deliberate visual language across every channel and pack (defined palette, motion signature, typography, intro sting) — a recognizable house style, the opposite of generic template output. Locked in a brand doc before any upload.
3. **Monthly proof-of-life screen-record.** Once a month, an unedited screen-capture of the engine running live — modules reacting to audio in real time — posted as a Short/community clip. Demonstrable human-built craft and originality on the record if YouTube ever reviews.
4. **Human curation in the loop.** `MAYA`/`KIN` select and re-work underperformers weekly against retention data — this is a curated channel with editorial judgment, not a fire-hose. Streams are moods, not spam.
5. **Original or fully-cleared audio only.** Every second is owned or CC0/licensed — no copyright strikes, no reused viral audio that flags as inauthentic.

---

## Free-fuel provider map (summary)

| Track | Lead agent | Free-fuel provider | Marginal cost |
|---|---|---|---|
| 1 · Module Packs | KIMI + empire-crew | AiHubMix free (glm-5.1) + Groq | ~$0 |
| 2 · YouTube streams | MAYA + Hermes | Gemini free + NIM (metadata); GPU render | ~$0 |
| 3 · Stock loops | empire-crew + KIN | Groq/Gemini free (metadata CSV) | ~$0 |
| 4 · Live VJ | KIN + KIMI | AiHubMix free (custom modules) | ~$0 |

## 90-day critical path (do in this order)

1. **Days 1–7:** Phase 0 core render loop working, verified by screen-record.
2. **Days 7–14:** Track 1 first pack live on Gumroad + Track 2 flagship 24/7 stream up. *(First revenue possible here.)*
3. **Days 14–30:** Daily Shorts pipeline automated; 2nd + 3rd streams; brand doc locked.
4. **Days 30–60:** Track 3 first 100 loops submitted; retention-optimization loop running weekly.
5. **Days 60–90:** Track 4 demo reel + service sheet; push Track 2 to 500 subs / 3,000 hrs; monthly proof-of-life clip #1 posted.

**Primary 90-day KPI:** YouTube Tier 1 cleared (500 subs + 3,000 watch-hrs) + first Gumroad revenue banked. Everything else compounds behind it.

---

*Save target per doctrine: `J:\WORKING-SERVER-ROOT\PLANS AND IDEAS\SYNCSYNTH_MONETIZATION_BUILD_PLAN.md` — one file, edit in place, no `_v2`.*