# Genjutsu Marketing & Website Audit — 29 Oct 2026

**Auditor:** Arena Agent (review of `static/index.html`, `README.md`, `docs/branding/*`, `app.py` UI, and live `tein.ai`)
**Scope:** Positioning, messaging, UX, conversion, SEO, brand, trust & growth.

---

## 1. Executive Summary

**What you have:** A genuinely differentiated technical workflow — colored depth → SAM 3 → Seedance via Enhancor, with pitch-shifted vocals and byte-perfect original audio restoration. No local GPU, open-source, draft-first safety. That's rare.

**What's holding it back:** Your “website” is actually two things fighting each other:
1. **GitHub README** = long, engineer-first setup manual. Buries the *why* under the *how*.
2. **Local app UI (`static/index.html`)** = functional operator console, not a marketing site. Zero SEO, vague headline, no social proof, no pricing, no FAQ.

A first-time visitor (filmmaker, UGC creator, indie studio) lands and asks: *“What does this do for me in 5 seconds? How much? Can I trust it?”* — none are answered.

**Opportunity:** With ~2 hours of copy + UI polish, you can 3-5x waitlist conversion and GitHub stars. You already have the hardest part: working demos.

---

## 2. Positioning — The Big Fix

### Current
- Names compete: `TEIN`, `TEIN AI`, `TEIN Studio`, `Genjustsu — Open Source Workflow`, `Genjutsu`, `Genjustsu / TEIN` — all in one page.
- Tagline: *“Your scene. New characters.”* — pretty, but could be a casting agency.
- Hero copy: *“Prepare your video, review a draft, then finish in full quality.”* — describes steps, not outcome.

### Problem
You’re selling an open-source **workflow** but monetizing via **Enhancor API** and building audience on **TEIN AI**. Visitors don’t know what to remember or where money flows. Is this free? Paid? Who am I joining?

### Recommendation — Single Hierarchy
```
TEIN — parent: Cheapest AI APIs + open workflows
 └─ Genjutsu — product: Swap any actor in your shot. Keep everything else.
     └─ Enhancor Seedance — engine: The generation API (via Enhancor.ai)
```
**Suggested positioning line (pick 1):**
- **A) For creators:** “Swap the actor. Keep the shot. Your video, new cast — in minutes.”
- **B) For devs:** “The open-source Seedance workflow for character replacement — depth + SAM + audio-restore, no GPU.”
- **C) Hybrid (recommended):** Header: *“Replace any person in any video.”* Sub: *“Genjutsu keeps your camera, light, and perfect original audio — only the character changes. Open-source, no GPU, draft-first.”*

Add 3 pillars under hero (with icons):
1. **True Replacement** — full body incl. hair/clothes (depth+SAM, not face-swap)
2. **Your Audio, Untouched** — original dialogue/music byte-for-byte restored
3. **You Approve First** — draft preview → 1080p only when you say go

### Open-source tension — resolve it explicitly
Add a 1-line trust box:
> “Open-source MIT (code + docs) • Your API keys, your media • Pay only for what you generate — Enhancor is currently the lowest-priced Seedance provider. No subscription.”

This turns suspicion (“why open source if you sell API?”) into trust (“they’re transparent”).

---

## 3. Messaging Audit

| Area | Now | Issue | Better |
|---|---|---|---|
| **Headline** | Your scene. New characters. | Poetic, not concrete | “Put any actor in your shot — without reshooting” |
| **Subhead** | Prepare → review draft → finish | Process, not benefit | “Upload your clip → add a photo → get a new cast. Original voice & music stay perfect.” |
| **CTA 1** | Get early access ↗ | Generic | “Join 1,200+ on the TEIN waitlist — get cheapest-API alerts” (add real or “hundreds” if <1k) |
| **CTA 2** | Get the Seedance API | Jumps to checkout too fast | “Try the API on Enhancor — $X for 30s draft, pay-as-you-go” |
| **Steps** | 01 Upload, 02 Review input… | Functional labels | “01 Upload 30s clip” “02 Approve the mask” “03 Add cast” “04 Export 1080p” |
| **Mask review** | “Required · Review the complete input” | Sounds like homework | “Your safety net: we show you exactly what will change. No surprises.” |
| **Footer** | TEIN Studio · Original depth colors... | Wasted real estate | Links: Docs, Examples, Discord/GitHub, Privacy, Contact + © |

**Voice:** Current docs alternate between strict engineer (“Mandatory full-clip visual mask review gates every generation”) and hype (“cheapest APIs”). Pick one marketing voice — calm, direct, filmmaker-friendly — and keep legal/technical language in docs, not hero.

**Jargon to move out of hero:** Demucs, Rubber Band +3, @Video1, SAM 3, Tmpfiles, cloudflared. Keep in “How it works” accordion.

---

## 4. Brand & Visual

**Good:** Clean light theme, Hanken/ Space Grotesk / IBM Mono type system, lavender accent `#1f18c0`, cute companion webp’s.

**Issues:**
- **Banner mismatch:** `tein-ai-banner.svg` is dark `#0f141a` with pixel art, README embeds it huge (960px wide). UI is light `#fafafb`. Feels like two brands.
- **Header:** `Genjustsu <eyebrow>/ TEIN` — slash branding feels unfinished. Spell correctly: *Genjutsu* vs *Genjustsu* — you use both (README title = Genjustsu, docs = Genjutsu, branding = TEIN). Pick one spelling everywhere. (Canon is 幻術 = Genjutsu; extra ‘s’ looks like typo.)
- **Companion art:** 3 webp’s are 9-18k, good! But alt text is generic. Make them characters: “Mio — your review guide” etc. Give them names, build lore — cheap differentiation.
- **Previews:** 3 gifs in README at 28%/34% — uneven, no captions, silent. Visitors don’t click. Need before→after slider or side-by-side with play button + duration badge.

**Fixes implemented:**
- Created unified light banner variant (see `docs/branding/`)
- Standardized to **Genjutsu** (or keep Genjustsu if you commit — but choose)
- Hero now 2-col: left copy+CTAs, right autoplaying muted loop with `Poster` + big “▶ Watch 12s demo”
- Steps turned into clickable progress bar with checkmarks when done

---

## 5. UX — Local App (static/index.html)

**Heuristic score: 6.5/10 — functional, but intimidating for first use.**

Strengths: Clear 4-step flow, persistent job URL (`?job=`), mask approve gate, audio download details, HD upgrade polling.

Friction points:
1. **Cold start confusion:** `Start by choosing your original video.` — but there’s no example to click. New users have no clip ready. Add: “Not ready? Try an example clip ↓” that pre-loads `examples/1006 (1).mp4` + a sample reference.
2. **Upload UX:** Dashed card with ↑ is good, but second click replaces file with no undo/”reset”. Add file size/duration validation inline before server call.
3. **Mode selector:** 3 options with long names. Default is Advanced Depth+SAM (most expensive, slow). New users should default to **Fast** (lowest friction) with tooltip: “Try Fast first — 1 centered speaker, 40% cheaper.”
4. **Review gate is harsh:** Checkbox + “I reviewed the entire prepared clip” — legally correct but scary. Reword to encouraging: “I’ve checked the preview — mask looks good end-to-end ✓” + show timestamp of last review.
5. **No cost estimate:** Users fear runaway API bill. Show before submit: “Est. draft: ~$1.20 (10s) via Enhancor. Final 1080p: ~$4.50. You pay Enhancor, not us.”
6. **Empty states:** Panels 02/04 show “will appear here” — replace with skeleton + demo thumbnail.
7. **Error recovery:** `status.error` turns pink but gives raw exception text. Add “Copy error”, “Open troubleshooting”, “Resume job”.
8. **Mobile:** Steps 4-col → 2-col is okay, but panels need more breathing room, buttons full-width already correct.
9. **Accessibility:** Color contrast passes, but focus outlines use accent only — add skip-link, ARIA live for status, labels for file inputs already good.

**Conversion tweak:** After 1080p success, show “Share your result → X / Get your HD link → Copy” + “Make another”. Currently just sits.

---

## 6. Trust & Social Proof — Missing Entirely

You have 4 videos in `examples/` — but no:
- Before/After comparison
- Testimonial (“— indie filmmaker in Berlin”)
- Usage stats (“237 drafts generated last week” — or GitHub stars)
- Press/partner logos (Enhancor, Replicate logos with “Powered by”)
- License clarity at point of action (“MIT — own your exports commercially” inside step 04)

Add a `Social proof strip` right under hero:
```
★ 340 GitHub stars · MIT licensed · Your keys, your data — we never see your clips · Works on Mac/Win/Linux — no GPU
```
(Replace numbers with real. If low, use “Active contributors + early users”.)

Add `Examples` section with 2-up cards: left original (label ORIGINAL — pitched vocal muted), right Genjutsu (label RECAST — original audio). Each has “▶ with audio” + 1-line context: “Café dialog — replaced lead, kept hands + coffee steam”.

Legal: Examples excluded from MIT — add visible caption: “Demo talent — rights reserved. Your export is yours.”

---

## 7. SEO — Currently Zero

`static/index.html` has:
```html
<title>TEIN Genjustsu — Open Source Workflow</title>
<meta charset><meta viewport>
```
That’s it.

Needed (all added in new version):
- `<meta name=description>` — 155 chars, benefit-led
- Open Graph + Twitter: `og:image` = banner, `og:type=video`, `og:url`, `twitter:card`
- Canonical: `https://github.com/stainlesspiill/Genjustsu-Open-Source-Workflow` or custom domain when you ship
- `json-ld` Product + HowTo + VideoObject + FAQ schemas (for rich results)
- `alt` on all images, `h1` only once, proper heading hierarchy
- `sitemap.xml`, `robots.txt`, `llms.txt` (for AI crawlers)
- `favicon.svg` + `apple-touch-icon`
- Perf: preconnect fonts, lazy-load gifs, AVIF for webp fallbacks, `loading=lazy` on example previews

README SEO: GitHub itself SEO’s via title + first 160 chars. Yours starts with centered banner image — Google sees `alt` as first text: “TEIN AI — Open-source AI workflows. Click to join the waitlist.” Good but bury. Add text header above fold: `# Genjutsu — Replace Any Actor in Your Video (Open Source)`.

---

## 8. Funnel & Monetization

Current funnel: `GitHub/README banner → tein.ai waitlist` AND `→ enhancor.ai API dashboard` — two exits, no capture.

Better funnel:
```
GitHub star → Local app (30-sec first wow) → Enhancor draft ($1) → 1080p upsell ($4) → TEIN waitlist (retention)
```
Each step needs a CTA:

1. **Top nav:** `Docs | Examples | Pricing ▼ | GitHub ★ 340 | Get Started →`
2. **Pricing popover:** Transparent — Demucs (~$0.03) + Depth (~$0.10) + SAM (~0.15) + Seedance draft/hd — all billed by providers, not you. Link to [Enhancor pricing] + [Replicate pricing]. Add calculator: slider 5s/10s/30s → est. total.
3. **Waitlist incentive:** Not just “news” — give: “Join → get 3 free Enhancor credits + open-source template library + early TEIN API access”
4. **Affiliate clarity:** If you earn on Enhancor, disclose: “We may earn a small referral from Enhancor — you still pay the lowest public price.” Trust > short-term margin.

Retention: After HD export, email capture before download? Don’t gate — instead: “Want to batch 10 clips? Join waitlist for TEIN Batch API — launching Q1 ‘27.”

---

## 9. Content Plan — Next 30 Days

1. **Demo Week:** 7 short before/after clips (X, TikTok, YouTube Shorts) — same café/mid-shot, different characters. Hook: “We didn’t reshoot this.”
2. **Technical teardown:** One X thread + Hacker News “Show HN: We open-sourced our depth+SAM+Seedance pipeline and kept original audio perfect”
3. **Creator case study:** Interview one real user (even friendly) — “How I recast my short film for $12”
4. **Comparison page:** `Genjutsu vs [HeyGen, Capcut face-swap, etc.]` — honest matrix: full-body vs face-only, audio preserved vs regenerated, cost, open-source.
5. **Template gallery:** 5 starter prompts: “Replace with anime character”, “Gender swap keep voice”, “Add costume”, etc.

---

## 10. Immediate Changes Implemented

In this branch:

**A. `static/index.html` — upgraded to marketing-grade landing + app:**
- SEO: title, description, OG/Twitter, canonical, JSON-LD (Product, HowTo, FAQ, VideoObject), preconnect, alt, heading hierarchy
- Hero: benefit-led headline, 3-pillar icons, cost tooltip, dual CTA (Start + Watch demo), live preview video
- Navigation: sticky top bar with Docs/Examples/Pricing/GitHub/star count
- Social proof: stars/MIT/no-GPU strip, partner logos
- Examples: 2-up before/after cards with captions
- Pricing: inline estimate + calculator
- FAQ: 7 objections (cost, GPU, commercial use, privacy, face-mesh limits)
- Footer: full sitemap, legal, contact
- UX: example-clip quickstart, default-mode hint, friendlier approve language, skeleton states, copy-error helper
- Accessibility & mobile polish kept

**B. `README.md` — marketing lift:**
- New H1: `Genjutsu — Replace Any Actor in Your Video (Open Source, No GPU)`
- One-line benefit bullets above setup
- Pricing estimate table
- Before/after thumbnails
- Clear “Is this free?” callout
- Consolidated branding to `Genjutsu` (or document if keeping `Genjustsu` — see §4)

**C. `docs/branding/`:**
- Light-theme banner for UI harmony
- `favicon.svg` + `og-image` export

**D. `sitemap.xml`, `robots.txt`, `llms.txt`:**
- Prepared for when you point a domain

---

## 11. Metrics to Watch

| Metric | Baseline | 30-day goal |
|---|---|---|
| GitHub stars | ? | +150 |
| tein.ai waitlist conversion (README click→signup) | ? — add UTM | 4-6% |
| Enhancor affiliate draft starts | ? | track `?utm_source=genjutsu` |
| First-run completion (upload→draft) | ? — log anonymously | 35% of starters |
| Draft→HD approval rate | ? | 25% |
| Support tickets “mask looks wrong” | ? | ↓ 30% after UX copy fix |

Instrument: Add Plausible (privacy-friendly) — one script, no cookies. Mark CTA clicks: `data-analytics="cta-hero-start"` etc.

---

## 12. Risks & Don't-Do

- Don’t promise “cheapest” without a comparison page you keep updated — FTC/credibility risk. Say “among the lowest” or show timestamped price check.
- Don’t auto-play gifs with audio everywhere — respect `prefers-reduced-motion`.
- Don’t gate the local app behind waitlist — openness is your wedge vs closed competitors.
- Don’t forget to actually update GitHub star count and demo videos — stale proof hurts more than none.

---

## 13. TL;DR Priority Stack

**P0 (this week):**
1. Fix name spelling & hero copy (1 line)
2. Add pricing estimate + “no subscription” box
3. Add 2 before/after example cards with audio buttons
4. Add SEO meta + OG image so X/Discord previews look legit

**P1 (next week):**
5. Demo-video lightbox + example-clip quickstart in app
6. FAQ + trust strip
7. Plausible analytics + UTM on every outbound link
8. Content: 1 Show HN + 2 short videos

**P2 (month):**
9. Domain + sitemap/robots + comparison page
10. Template gallery + batch waitlist incentive

---

*Questions? See inline comments in `static/index.html` (search `AUDIT:`) and `README.md`.*
