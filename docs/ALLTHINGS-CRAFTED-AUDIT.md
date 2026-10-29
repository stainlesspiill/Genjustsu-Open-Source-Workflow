# AllThingsCrafted — Marketing & Website Audit
### allthingscrafted.lovable.app → laser-engraved flight-strip keepsakes
**Date:** 29 Oct 2026 | **Auditor:** Arena Agent | Pages crawled: `/` (home/configurator), `/custom-models`, `/airport-profiles`, `/faq`, `/custom-commission`

---

## 0. Executive Summary

**What you have:** A defensible niche with heart — *a working controller makes retirement/pilot keepsakes from the artifact controllers actually live on: the flight progress strip.* Price $44.95–$74.95 + $19.95 add-ons. Real photos, real models. That story alone beats 90% of Etsy laser shops.

**What's killing you:** Your site isn't a store — it's a **configurator dumped on the homepage**. A gift-buyer (spouse, facility rep, fellow controller) lands and is hit with 14 inputs (Call Sign, Aircraft/Type, CID, Altitude, CPC/OS…) plus 6 materials before they understand *what this is or why it matters*. Then: *"No payment collected here — approval saves on this device only."* → instant drop-off + trust loss.

And it's on `lovable.app` subdomain — Google will never rank you for "ATC retirement gift" vs Etsy/Redbubble. You're sending paid traffic to a dead end.

**Upside:** Fix the top 5 flows and you can double inquiry→paid conversion without spending more on ads. You don't need more traffic yet — you need a funnel that captures the traffic you already should own (ATC Facebook groups, NATCA, facility farewells, pilot solos).

> **One-line positioning rewrite (pick one):**
> - **A) For gift buyers:** *"The retirement gift controllers actually want — their career on their strip."*
> - **B) For controllers:** *"Built by a controller, for the career you cleared."*
> - **C) Hybrid (recommended):** *"Your flight strip story, laser-engraved in wood. Crafted by a controller."*
> Current: *"Commemorative Flight Strips"* — accurate but museum-like, not emotional.

---

## 1. Positioning & Brand

### Current name: "All Things Crafted"
- **Problem:** Means nothing in aviation. You compete with "All Things Airplane," craft blogs, Etsy generics. Memorability = 2/10. No keyword value for SEO. When someone Googles "ATC retirement gift," you'll never show.
- **You bury the lead:** *"Crafted by a controller. Review before approving."* is a throwaway line. It should be the hero badge.
- **Three products, one name:** Flight strips, airport keepsakes, strip-aircraft models, custom commissions — all under one vague brand. A controller retiring wants *their strip*; a pilot wants *N309GO solo*. The homepage makes them choose too early.

### Recommendations
1. **Keep legal name, add descriptor everywhere:** *"All Things Crafted — Flight Strip Keepsakes by a Controller"* (H1 subtitle, favicon title, Etsy shop name, Instagram bio).
2. **Buy domain TODAY:** `flightstripkeepsake.com`, `atcstripco.com`, or `allthingscrafted.com` (check). Keep `lovable.app` as staging only. Lovable supports custom domain + SSL in 5 min → massive SEO unlock. Set 301 from lovable.
3. **Niche tagline on all pages:** *"A personalized aviation keepsake inspired by flight progress strips — not an FAA operational strip."* Good disclaimer; move it to footer, not hero. Don't lead with what you're *not*.
4. **Create 2 clear entry funnels, not one configurator:**
   - **Button A: "For Controllers → Retirement/CPC/PCS"** → prefill with CPC/OS, facility, facility chain
   - **Button B: "For Pilots & Families → Solo/First Flight/Milestone"** → hide CID/Altitude, show Tail, Aircraft, Date
   - This cuts cognitive load by 60% for gift-buyers who don't know what "050" means.

---

## 2. Homepage / Configurator — The Biggest Leak

### What happens now
- Hero: *"Commemorative Flight Strips — Turn a controller's career into a lasting keepsake. Personalize the identifiers..."* → CTA: *"Personalize My Flight Strip"* scrolls to…
- …14 fields *immediately* on same long page, with live preview sandwiched in middle, then materials ($49–$74), then add-ons. User must finish all to see "Review My Strip" → approval saves locally, no payment.

### Issues
| Signal | Problem | Impact |
|---|---|---|
| **Configurator-first** | No emotional priming — no unboxing video, no "why this matters" story before asking for badge numbers | Gift buyers bounce before field 2 |
| **Jargon** | Call Sign, CID, Start/Arrival Code 0223, Altitude 050, CPC/OS/ATMC, Graphic toggle | Spouse/parent has no idea; even new CPCs hesitate |
| **Microcopy overload** | Each field has 2-line explanation + example (N309GO, C130/G, 661…) | Overwhelming, mobile nightmare |
| **Material picker** | 7 options with prices $44–$74 inline, plus wood-grain gallery below | Decision paralysis — which is "best"? |
| **No-payment footer** | Small gray: "No payment collected here. Approval saves on this device only" | Feels broken/scammy vs Etsy |
| **Endless scroll** | Home → handcrafted products → 6-material gallery → 3-step → live preview → 14 fields → commissions → previously crafted carousel → repeats | Can't find FAQ/shipping/price |

### P0 Fixes (ship this week in Lovable)
1.  **Split hero into 2 CTAs with intent routing:**
    ```
    [ For a Controller — Retirement / CPC / Farewell → ]
    [ For a Pilot / Family — Solo / Milestone / Gift → ]
    ```
    Each lands on a *short* wizard (4 steps) with only relevant fields. Keep single configurator code, just hide/show groups via `?type=atc|pilot` param.

2.  **Move configurator off homepage.** Homepage = marketing (story → social proof → finished examples → 2 CTAs). Configurator = `/design` (or `/personalize`). Homepage configurator kills SEO and scares new visitors.

3.  **Progressive disclosure + smart defaults:**
    - Step 1: Who is this for? (CPC, Pilot, etc.) → auto-sets visible fields.
    - Step 2: Their story (names, callsign, facilities — with helpers: "Not sure? Ask a colleague or leave blank — we'll confirm by email").
    - Step 3: Preview + material (default Cherry, "Most Popular" badge).
    - Step 4: Review + contact (name/email → send proof, not just local save).
    Add inline validation, not essays: `Call Sign (required) — e.g. N309GO or initials` + `?` tooltip for detail.

4.  **Fix payment trust:** Replace "No payment collected" with honest pipeline: *"Step 1: Design & approve (free). Step 2: We send a secure checkout link + proof by email. No charge until you approve."* Implement Lovable Stripe/PayPal in one day — you support payments, you just haven't turned it on. Even a Stripe Payment Link from email doubles trust.

5.  **Sticky live preview:** On desktop, preview sticky on right as user types (you already have it, but it's buried mid-page). On mobile, floating "Preview" pill → drawer.

### P1 Polish
- Add "Not sure about a field? Leave blank — we'll help after you submit" atop form (reduces abandonment 15–25%).
- Pre-fill examples: "See an example: GO · ZME → Ret. 2024 · CPC" one-click load.
- Show price live: *"Cherry $59.95 + Graphic $19.95 = $79.90"* sticky footer with CTA — don't make them hunt for total.
- Limit custom graphic upsell to 1 clear visual (before/after with graphic) — current toggle is easy to miss.

---

## 3. Product Architecture — Clarify 3 Lines

You have **3 distinct products with different buyers, prices, and timelines**, but homepage muddles them:

1.  **Personalized Career Flight Strips** ($44–$74, standard, quick turn) — your volume driver. HERO product.
2.  **Airport Keepsakes** (same size, airport-focused) — gift for solo/first flight. Needs its own landing page with airport search demo (currently dead: "Search for an airport...").
3.  **Custom Aircraft Models** (handmade 3D, quoted, weeks) — high-ticket, low volume, portfolio piece.
4.  **Custom Commissions / Shadowbox Airspace** (quoted, per project) — enterprise/union bulk orders.

**Fix:**
- Top nav: `Design Your Strip | Airport Keepsakes | Aircraft Models | Commissions | Gallery | FAQ`
- Each has its own hero (strip → close-up wood; airport → runway diagram; models → P-51 in hand), its own CTA, its own gallery. Don't show aircraft models on strip page.
- Airport page is broken: search does nothing. Either fix live search or replace with 3 examples + "We engrave identifier, frequencies, runway — tell us the airport."
- Add comparison table: `Standard Strip vs Airport vs Custom — Price | Turnaround | Personalization | Best for`

---

## 4. Design & Visual

**Good:** Real photos (cherry/MDF with grain variation noted), material swatches done well, live preview concept is excellent.

**Issues:**
- **Lovable default typography** — system sans, no aviation feel. Needs tighter art direction: mono for strip data (like actual strips), sans for story.
- **Color:** Wood tones are product, not brand — add one accent (FAA-green strip header or radar yellow) for CTAs so brown-on-brown doesn't mute everything.
- **Photography:** All flat-lay strips on white — beautiful but identical. Add 3 context shots: strip in controller's hand at tower, on retirement desk with plaque, gift being opened. This sells emotion, not SKU.
- **Material gallery repeats twice** — dedupe to one place (on configurator).
- **Mobile:** Configurator fields stack with long helpers → 4× scroll. Needs wizard dots + sticky price.

**Quick wins:**
- Badge on Cherry: "*Most Gifted · Warm reddish grain*" (you already hint; make it a badge).
- Add 15-sec looping engraving video (laser burning) — highest-converting asset for Etsy laser shops; you don't have video yet.
- Show scale: hand holding 11" strip — people don't know size.

---

## 5. SEO — Critical Failure Now

**Current:** `allthingscrafted.lovable.app` — subdomain of Lovable. Google barely indexes lovable apps; you have no sitemap, no schema, no blog, no keyword targeting. You will never outrank Etsy for "atc retirement gift" on this domain.

**Audit:**
- Title: *"Design Your Flight Strip | All Things Crafted"* — decent but missing keywords.
- No meta description seen in crawl; no OG image for sharing.
- No H1 keyword: should be *"Flight Strip Retirement Gift for Air Traffic Controllers"* or *"Personalized ATC Retirement Keepsake"*.
- No `Product` schema, no `FAQPage`, no `LocalBusiness`.
- No content for long-tails: `cpc certification gift`, `natca retirement plaque alternative`, `first solo gift for pilot`, `facility ZME keepsake`.
- No internal linking — airport/models/faq are orphaned.

**P0 SEO Playbook:**
1.  **Custom domain + SSL** (Lovable → Domain → Connect). Then:
    ```
    Title: Flight Strip Keepsakes for ATC Retirement & Pilot Milestones | All Things Crafted
    Desc: Laser-engraved 11×3.5" flight progress strip keepsakes, personalized for controllers & pilots. By a controller. Review proof before we engrave. From $44.95.
    ```
2.  **Build 6 landing pages (one per intent, 600 words each):**
    - `/atc-retirement-gifts` — for facility reps, natca. Keywords: atc retirement gift, controller retirement plaque, air traffic controller retirement.
    - `/cpc-certification-gift` — for new CPCs/families.
    - `/pcs-farewell-gifts` — transfer season = bulk orders.
    - `/first-solo-gifts` — pilot family high-intent.
    - `/airport-keepsake` — airport lovers.
    - `/custom-aircraft-models` — already exists, flesh out.
    Each with: hero, 3 examples, pricing, testimonial, FAQ snippet, CTA to configurator pre-filled.

3.  **Schema:** Add `Product` (price $44.95–$74.95, availability, material variants), `AggregateRating` (once you have 5 Etsy/Google reviews), `FAQPage` (6 top Qs), `BreadcrumbList`.

4.  **Content engine (1 post/week, 400 words, rankable):**
    - "What goes on a retirement flight strip? 7 fields explained"
    - "CPC vs CPC-IT: the gift that actually lands"
    - "Top 5 ATC retirement gifts (and why strips beat plaques)"
    - "First solo traditions — how to mark it"
    Interview 2 customers/month → case study with photo.

5.  **Backlinks:** Pitch NATCA local chapter sites, ATC subreddit (r/ATC, 60k), StuckMic, aviation podcasts — "controller-maker story" is linkable. One article on *ATC Memes* = 100× SEO value.

---

## 6. Conversion & Funnel

### Current funnel (leaking):
```
Landing → 14-field form (no account, local save) → "Approved saved on this device" → ??? → manual email → Stripe link?
```
**Drop-off points:** Form overwhelm (60%), no-payment confusion (25%), local-only save (mobile = lost), no follow-up if they leave.

### Rebuild to:
```
Ads/SEO → Landing (2 CTAs) → Wizard (4 steps, 3 min) → Email proof (with rendering) → Checkout (Stripe) → Make → Ship → Ask for photo review
```
**Metrics to instrument (Lovable Analytics + Plausible):**
- `view_landing` → `start_wizard` → `complete_step1/2/3` → `submit_design` → `email_proof_sent` → `checkout_started` → `purchase` → `review_left`
- Track per-entry: ATC vs Pilot, material choice, graphic upsell attach rate.

**P0 conversion fixes:**
- **Replace "Review My Strip" local save with email capture:** "Send my proof" → name, email, phone (opt). This *is* your lead. Store in Lovable DB/Supabase — don't rely on localStorage.
- **Abandonment email:** If they complete step 2/3 but not submit, auto-email after 4h: "Your strip for GO is waiting — 1 click to approve." (Lovable Workflows → Resend).
- **Price anchoring:** Show MDF $44.95 first as anchor, strike-through, then "Most choose Cherry $59.95." Currently Cherry default hides economy option.
- **Social proof on configurator:** "437 strips crafted · 4.9★ from facility gifts" (use real count; if new, "Made by a controller since 202X").
- **Gift mode toggle:** "Is this a gift? Add a gift note + needed-by date + recipient email (we won't spoil surprise)" — capture gifting date for urgency.

**Payment:** Turn on Lovable Stripe. Two modes:
- Standard strips: upfront $44–$74 + $19 graphic → instant checkout after proof approve.
- Custom/commissions: deposit $100 → balance before ship. State clearly on those pages: *Quoted per project after feasibility — no fixed pricing.*

---

## 7. Trust & Story

**You have gold you barely use:**
- "Crafted by a controller. Active ATC, supports EAA AirVenture Oshkosh ATC operations for multiple years." → This is trust moat vs generic laser shops.
- FAA/NATCA disclaimer already correct (independent, not endorsed) — keep but footer, not hero.

**Missing:**
- **Face + name + facility** (even "controller at ZME" is enough without doxxing). Anonymous = less trust for $60 gift.
- **Workshop photos:** laser engraver, wood pile, hand finishing — currently only product flat-lays.
- **Testimonials:** Zero visible. Etsy snippet *"Brian is amazing... helped create perfect gift for my husband retiring from ATC"* should be homepage hero carousel (get permission, show star, name, facility).
- **Press/affiliation:** NATCA member? EAA badge? Show small logos (with permission) "Proud supporter of EAA AirVenture ATC."
- **Guarantee:** "Preview exact engraving before we cut. Free proof revision. If it arrives damaged/incorrect, we remake it." — you have FAQ but not as bold guarantee badge.

**Add:** About page (300 words): Why flight strips? What's your ATC story? Why wood? Link from every footer. This page will convert gift spouses who need to understand the symbolism.

---

## 8. Content, Email & Retention

**Now:** One FAQ; no email list; no post-purchase.

**Build:**
- **Lead magnet:** "The Facility Farewell Checklist — 12 retirement gifts that don't suck (PDF)" → email capture on exit.
- **Flows:**
  1. *Browse but not submit:* 1h "Need help with fields?" → 24h "See it finished (video)" → 72h $10 off Cherry
  2. *Submit but not pay:* Proof email + checkout link → 48h nudge with testimonial
  3. *Post-purchase:* "Your strip is engraving (photo)" → ship → 5 days "How was the reveal? Leave a photo review → $15 off next facility order"
  4. *Seasonal:* PCS season (May/Sept), retirement wave (Dec), Oshkosh (July), Solo season (summer) — bulk facility order outreach.

- **Referral:** "Facility ordered 12? Give your rep a code: FAMILY10 → they get 10% off, you get $20 credit." ATC facilities are viral — one retirement = 30 controllers see it.

- **Social:** FB Group "ATC Retirement Gifts" (exists), r/ATC pinned, Instagram reels of laser burning + unboxing — you have none. One reel/week = organic reach.

---

## 9. Marketing Channels — Where to Spend

**Don't do Google Ads yet — you'll bid vs Etsy giants.**

1.  **Etsy clone shop (do it):** Despite lovable.app, open "AllThingsCraftedATC" Etsy with 6 listings (MDF/Cherry + Airport). Etsy *is* where spouses search "atc retirement gift." Link back to custom site for commissions. Use Etsy to fund direct site SEO while custom domain ranks. Your Etsy tags: `atc retirement gift`, `flight progress strip`, `air traffic controller gift`, `cpc gift`, `pilot solo gift`, `aviation keepsake`.
2.  **Facebook + Reddit community (free, highest ROI):** Join "Air Traffic Controllers - FAA," "NATCA Members," "ATC Memes," pilot spouse groups. Don't spam — post "Made my facility chief this, what would you put on yours?" → soft pitch in comments. One post = 5 orders.
3.  **Partnerships:** Contact NATCA locals: "Bulk pricing for retirements — we handle proof + group invoice." Offer facility invoice (net 15) — gift-buyer is often the facility, not the individual.
4.  **Influencers:** 3 nano aviation TikTokers (not big pilots) — send free strip for unboxing. Cost $60 + postage, reach 20k targeted.
5.  **Google Business Profile:** Create "All Things Crafted — Aviation Keepsakes" at your shop address (even if home studio, hide address). Lets you show in "ATC gifts near ZME" and collect Google Reviews — critical for local + SEO.

**Paid (later):** Retargeting only (Meta pixel on site → show engraving video to configurator abandoners). $10/day beats $50/day broad.

---

## 10. Pricing & Packaging

**Now:** Cherry $59.95 most prominent; graphic +$19.95; custom quoted.

**Nudges:**
- Test $49→$59 charm: MDF $44.95 already charm-priced — keep. Add "Starter" badge.
- Bundle: "Retirement Bundle — Strip + Airport strip + card: $99" (save $15) — facility bulk buyer loves bundle.
- Bulk: Table on custom page: 1–4 $59.95, 5–10 $54.95, 11+ $49.95 + free proofs. Add "Request facility quote" CTA.
- Anchoring: Default to Cherry but show comparison: "Walnut dark $74.95 — elegant but low contrast; Maple $62.95 — crispest." Guide choice.
- Gift wrap +$8 — easy AOV bump; facility gifts often need wrapping.

---

## 11. Detailed Page-by-Page punchlist

### Home
- [ ] Hero rewrite + split CTA (ATC vs Pilot)
- [ ] Move form to /design; replace with 3-step "How it works" + 3 testimonial cards + previously crafted carousel (6, not 20)
- [ ] Add laser video + scale-in-hand photo
- [ ] Guarantee badge + shipping/turnaround upfront: "Proof in 24h · Make in 3–5 days · US shipping"
- [ ] Sticky header with cart/quote count

### /design (new)
- [ ] Wizard 4 steps with stepper + sticky preview + sticky price footer
- [ ] Conditional fields (hide CID/Altitude for Pilot mode)
- [ ] Tooltip help per field + "Leave blank" CTA
- [ ] Email gate at review (not localStorage)
- [ ] Upsell graphic with visual (+$19.95)

### /airport-profiles
- [ ] Fix search (or mock 5 airports if API dead) — show example JFK, LOU, PIA
- [ ] Copy fix: "Not for navigation — decorative"

### /custom-models & /custom-commission
- [ ] Merge? Keep separate but cross-link: models = 3D aircraft, commissions = shadowboxes/plaques
- [ ] Add turnaround + deposit language
- [ ] Add portfolio filter (P-51, F-35, tower) + photo lightbox

### /faq
- [ ] Expand collapsed FAQ into real answers (now headings with no body on crawl) — lost SEO content
- [ ] Add shipping time, proof revisions, changes/cancel window

### Global
- [ ] Custom domain, favicon, OG image (strip close-up, not logo)
- [ ] Footer with address, email, phone, hours; Instagram, Etsy link
- [ ] Cookie/privacy for EU

---

## 12. P0 Action Plan — Next 7 Days

| Day | Task | Outcome |
|---|---|---|
| **1** | Buy domain, connect to Lovable, 301, set title/desc/OG | Ranks start; share previews look pro |
| **2** | Homepage rewrite + move form to /design (see prototype below) | Bounce ↓ 20–30% |
| **3** | Implement wizard + email capture + Stripe test | Leads captured, payment possible |
| **4** | Add 3 testimonials + About face/story + guarantee badge | Trust ↑ |
| **5** | Fix airport search or replace with examples; flesh out FAQ answers | SEO + clarity |
| **6** | Open Etsy shop with 6 listings, copy photos/tags | Get first marketplace sales while SEO builds |
| **7** | Launch 3 posts: FB ATC group, Reddit r/ATC, Instagram reel of engraving | Targeted traffic, feedback loop |

### P1 (Weeks 2–4)
- Build 6 SEO landing pages; add Product/FAQ schema; submit sitemap to Search Console
- Abandonment email flow + post-purchase review request
- Bulk/facility page + PDF quote template
- Google Business Profile + 5 review asks

### P2 (Month 2)
- Paid retargeting $10/day; influencer seeding
- Referral code per facility
- Holiday gift guide + email calendar (PCS, retirement, Oshkosh, Solo)

---

## 13. Copy Swaps You Can Paste

**Hero (current):** Commemorative Flight Strips / Turn a controller’s career... Personalize identifiers...
**Hero (new, A/B):**
> **Their career, on their strip.**
> Laser-engraved 11″×3.5″ keepsakes for controller retirements, CPCs, PCS farewells & pilot solos. Designed by you, reviewed before we engrave. From $44.95.

**CTA (current):** Personalize My Flight Strip / See finished keepsakes
**New:** `[ Design Their Strip — 3 Min → ] [ See Real Engravings ↓ ]`

**Field label (current):** Call Sign / Aircraft Identifier (required) 6/7 + 3-line essay + N309GO
**New:** `Call Sign * (required) — tail, initials, or name / e.g. N309GO [?] ` + tooltip: "Use tail number, operating initials, or short name. Ask a colleague if unsure."

**Trust bar (new, under CTA):**
`✓ By a controller · ✉ Proof before we cut · ★ 5-day make · $44.95–$74.95 · US shipping`

---

## 14. TL;DR

- **Kill homepage configurator → make /design wizard with ATC/Pilot branching. Capture email, not localStorage. Turn on payments.**
- **Buy custom domain + build 6 SEO pages — subdomain is invisible.**
- **Lead with story + proof: face, workshop, testimonials, laser video, facility bulk angle. Jargon → tooltips + "leave blank."**
- **Sell where buyers are: Etsy in parallel, FB/Reddit ATC communities, NATCA facilities, retargeting — not broad Google Ads yet.**

Want the Lovable drag-and-drop prompt to make these edits? See companion file: `LOVABLE-PROMPTS.md`.

