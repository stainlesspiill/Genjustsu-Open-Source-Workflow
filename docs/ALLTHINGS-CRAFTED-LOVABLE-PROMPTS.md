# Lovable Prompts — Paste into allthingscrafted.lovable.app to implement P0
Copy each block into Lovable chat (one at a time). Test on preview link before publishing.

---

## 1) Homepage hero fix + split CTAs

```
Rewrite the homepage hero. Keep the brand but change:
- Eyebrow: "Flight Strip Keepsakes · By a Controller"
- H1: "Their career, on their strip."
- Sub: "Laser-engraved 11×3.5″ keepsakes for controller retirements, CPCs, PCS farewells & pilot solos. Designed by you, reviewed before we engrave. From $44.95."
- Replace the single "Personalize My Flight Strip" CTA with TWO buttons side-by-side:
  [Design for a Controller →] links to /design?type=atc
  [Design for a Pilot/Family →] links to /design?type=pilot
  Under CTAs add trust bar in small mono: "✓ By a controller · Proof before we cut · 5-day make · US shipping"
- Keep secondary CTA "See Real Engravings" scrolling to Previously Crafted.
Do not touch the configurator code yet.
```

## 2) Move configurator off homepage to /design wizard

```
Create a new page at /design that contains the entire current configurator (all fields, live preview, materials, graphic option, total, Review My Strip). 
On the homepage, REMOVE the inline configurator and live preview fields entirely. Replace that section with a new "How it works" block:
- 3 cards: 1 Add their details — 2 Preview & choose material — 3 Review & approve (with 14s engraving video placeholder)
- Then a centered CTA: [Design Their Strip — 3 Min →] to /design
- Then show Previously Crafted carousel (keep existing images).
The live preview and form should ONLY live on /design going forward.
```

## 3) Wizard with branching (ATC vs Pilot)

```
On /design, convert the long single-page form into a 4-step wizard with a top stepper (Step 1/4 dots) and sticky live preview on the right (desktop) or floating Preview pill on mobile, and sticky price footer (Base + Add-ons = Total + [Send My Proof →]).
- Step 1: Who is this for? Radio cards: "Air Traffic Controller (Retirement/CPC/PCS)" vs "Pilot / Family (Solo, Milestone)". This sets ?type=atc|pilot and controls visible fields.
- Step 2: Their story — show only relevant fields. For ATC: Call Sign*, Facility, Position/CPC, Dates. For Pilot: Call Sign/Tail*, Aircraft, Dates. Hide Altitude/CID/Computer ID unless user clicks "Add more details". Every field has short helper + tooltip (?) with the long text. Add banner: "Not sure about a field? Leave blank — we'll help after you submit."
- Step 3: Preview & material — show enlarged preview + material picker (7 options with prices, default Cherry with "Most Popular" badge, MDF $44.95 with "Budget" badge).
- Step 4: Review & approve — show final engraving at 100% + contact form: Name*, Email*, Phone, Needed-by Date, Gift note. CTA: [Send My Proof →] (not "Review My Strip"). Submitting saves to database and sends email, not just localStorage. Keep validation.
Use URL param ?type=atc|pilot to pre-hide fields. Keep all field bindings working.
```

## 4) Pricing + payment trust

```
Update pricing display everywhere:
- Sticky footer on /design shows live: Base — Cherry Hardwood $59.95 + Add-ons $0.00 = Total $59.95
- On homepage handcrafted section, add 3 pricing cards with badges: MDF $44.95 Budget · Cherry $59.95 Most Gifted · Walnut $74.95 Elegant
- Replace the tiny gray "No payment collected here. Approval saves on this device only." with a clear 2-step box:
  [1] Design & approve — free. We send a proof by email.
  [2] Approve proof → secure checkout. No charge until you approve. Add a disabled Stripe placeholder button: [Secure Checkout — after proof approval]
- Enable Lovable Stripe in Settings → Payments (test mode first). Standard strips = upfront payment after proof. Custom commissions = deposit $100 then balance. We'll wire later.
```

## 5) SEO + trust injection

```
Add global SEO and trust:
- Set site title: "Flight Strip Keepsakes for ATC Retirement & Pilot Milestones | All Things Crafted"
- Meta description: "Laser-engraved 11×3.5 flight progress strip keepsakes, personalized for controllers & pilots. By a controller. Review proof before we engrave. From $44.95."
- Add favicon (strip icon), OG image (close-up cherry strip), canonical to future custom domain.
- On homepage after hero, add a trust strip: star rating (use ★★★★★ 4.9 · 437 strips crafted — replace with real count if different), "By active controller · EAA AirVenture ATC supporter", "Proof in 24h · Make in 3–5 days".
- Add a new About snippet above footer: 2 columns — left: photo of maker in tower/at workbench (use placeholder workshop image for now) + caption "By [Name], controller at [Facility] — supporting EAA AirVenture Oshkosh for multiple years." Right: 120-word story about why flight strips matter + guarantee badge: "Exact proof before we cut · Free revision · Remake if damaged/incorrect".
- Expand FAQ answers: currently headings with no body in crawl — write full 2-sentence answers for Ordering & Payment, Production, Shipping. Keep link to /faq.
```

## 6) Nav + footer

```
Update top nav to: Design Your Strip (/design) | Airport Keepsakes (/airport-profiles) | Aircraft Models (/custom-models) | Commissions (/custom-commission) | Gallery (homepage #previously-crafted) | FAQ | CTA button "Design Their Strip →" to /design
Footer: add 4 columns — 1 Brand + tagline + Instagram/Etsy icons, 2 Products (links to 3 product pages), 3 Support (FAQ, Shipping, Contact), 4 Contact (email, phone placeholder, "Independent — not affiliated with FAA/NATCA"). Add address line for future Google Business Profile.
```

---

## After P0 — copy-paste for Etsy & social

Provide these to your Lovable AI to export:
- Etsy listing titles/tags (see audit) + 7 photos per listing.
- Abandonment email copy (from audit §6/8).
- FB group post template (not spammy).

