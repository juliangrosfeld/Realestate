# RE/MAX BonBini Curaçao — Webflow Build Blueprint

**Prepared for:** RE/MAX BonBini Curaçao (Nick Vervoord, Joost Houtsma, Chris Vervoord, Thom Vervoord)
**Subscription tier:** $1,500/month
**Existing site under upgrade:** realestate-curacao.com
**Locales at launch:** EN (primary), NL, ES, DE
**Currencies:** USD primary; EUR + XCG toggles
**CMS:** Webflow native (Components, Variables, Localization Advanced, Logic)

---

## 1. Strategic positioning

### Who this agency is to its market

RE/MAX BonBini is the #1 best-selling real estate agency in Curaçao. The agency combines the global RE/MAX network — the only Curaçao agency with that reach — with twenty years of on-island specialization, three physical offices spanning Jan Thiel, Blue Bay, and Coral Estate, and a transaction footprint that spans entry-level apartments through The RE/MAX Collection ultra-prime stock and the exclusive sales engagement for The View Resort & Marina.

The site has to read like the market leader speaking. Not louder — quieter, more confident, more specific. The competitive field in Curaçao has 10–20 boutique luxury agency sites; most lean on the same template-Caribbean visual language (overcooked sunsets, palm-leaf accents, generic "your dream home awaits" copy). The opportunity is to do the opposite: a quiet, well-edited magazine of a website where the photography and the local expertise carry the weight, with the global RE/MAX rails behind everything.

### Three priority buyer archetypes

**1. The Dutch second-home buyer (primary)**
A 45–65-year-old Dutch professional or owner-operator buying a second home for 2–4 months of personal use plus vacation rental income. Speaks Dutch first, comfortable in English. Values Dutch legal framework familiarity (eigendom, Kadaster, civil-law notary), the BRK tax treaty, daily KLM connections, and Curaçao's "Dutch-but-tropical" framing. Search terms: *huis kopen Curaçao, villa Jan Thiel, vakantiehuis Curaçao.* Switzerland-based Dutch expats are a known sub-segment.

**2. The North American investor / lifestyle buyer**
US or Canadian, 50–70, retiring or pre-retiring. Buys for vacation use plus yield, often with the investor-permit pathway in view. English-only. Hot buttons: no foreign-ownership restrictions (rare in the Caribbean), Dutch legal stability, ~3.5 hours from Miami, outside the hurricane belt, capital gains tax of zero on private residences, the $280K / $425K / $850K investor-permit ladder leading to a Dutch passport route after five years.

**3. The European yield investor (German, Belgian, Swiss-Dutch)**
40–60, financially literate, pre-tax-optimization mindset. Buys for vacation rental yield plus family use. Values transparency on yields, the 7% lodging tax convention, capital-gains-zero treatment, and professional property management. German-language site copy is a meaningful conversion lever for German buyers — this is one of the reasons DE is launching alongside EN/NL/ES.

A fourth segment — local Curaçaoan upgraders — is served by the agency but does not lead the website narrative. Papiamentu is intentionally not in the launch locale set because the site's positioning is foreign-buyer-led; a future PAP locale can be added if the agency wants stronger on-island brand signaling.

### Differentiation — three promises the website makes

1. **The agency that's already done it.** Twenty years on the island, founded in 2005, RE/MAX franchise since 2006, owner-operator continuity through the 2024 transition. Twenty-plus agents, three offices. The data behind every valuation comes from cooperation with Brouwer Taxaties, the leading appraiser. Not a startup, not a side project.
2. **Reach and access most agencies can't match.** Only Curaçao agency on the global RE/MAX network. The RE/MAX Collection — the luxury sub-brand — for >$1M and exceptional homes. Exclusive partner of Blue Bay Golf & Beach Resort since 2009. Exclusive sales office for The View Resort & Marina. First Curaçao agency fully compliant with FIU regulations, in a market where no agent licensing exists. These are the unfair advantages.
3. **Local fluency that rewards the buyer.** Site walks Dutch, American, and Latin/EU buyers through eigendom vs. erfpacht, the kosten koper convention, the investor permit ladder, and the realistic 6–12-week notary timeline — in their own language. The site demonstrates expertise instead of claiming it.

---

## 2. Sitemap

```
Home

Properties (hub)
├── For sale
├── For rent (long-term)
├── New developments
│   └── The View Resort & Marina (featured project landing)
├── The RE/MAX Collection (luxury sub-brand experience)
├── Commercial
├── Lots / land
└── Off-market / private listings (gated, Collection-buyer access)
Property detail (CMS template — single template, status-aware variants)

Neighborhoods
├── Neighborhoods index
└── Neighborhood detail (CMS template)

Buying
├── Buying guide (long-form hub)
├── Eigendom vs. erfpacht
├── Kosten koper / buyer's costs
├── Mortgages (residents & non-residents)
└── Investor permit pathway

Selling
├── Sell with us
├── Marketing package (what we do for sellers)
└── Recent sales (anonymized track record)

Investors
├── Investor home (yields, ROI, structures)
├── Vacation rental ROI analysis
├── SPF / holding structures (info, not advice)
└── Investor permit pathway (cross-linked from Buying)

About
├── About BonBini
├── The leadership team (Vervoord / Houtsma)
├── Agents (CMS template — agent grid + detail)
├── Offices (Jan Thiel HQ / Blue Bay / Coral Estate)
└── Our compliance commitment (FIU)

Insights / Market updates (CMS-driven)
└── Article detail (CMS template)

Contact

Legal
├── Privacy policy
├── Cookie notice
├── Terms
└── Disclaimer
```

**CMS-driven templates:** Property detail, Neighborhood detail, Agent detail, Insights article. The View Resort & Marina is a hand-designed landing page (not CMS), pulling individual unit availability from a separate Properties-collection filter (`Development = The View`).

**Removed vs. defaults:** No Vacation Rentals tab — agency is sales-and-long-term-rental focused, not a vacation rental manager. Vacation rental ROI lives in the Investors hub instead.

---

## 3. Visual system

### Design philosophy

Confident understatement, dual-tier. The primary RE/MAX BonBini experience holds the franchise brand in a more refined, magazine-style execution than the standard RE/MAX template — same red/white/blue equity, but framed with generous white space, refined serif headlines, and photography that does most of the talking. The RE/MAX Collection sub-brand experience steps further away from franchise standards into a distinctly more premium expression — same parent, clearly different visual register. Treat the relationship the way Sotheby's International Realty relates to Sotheby's auction: shared lineage, different audience, separate visual rules.

### Type — primary brand

| Token | Family | Notes |
|---|---|---|
| Display / headlines | **Fraunces** (variable) | Modern, slightly editorial serif. Free, Google Fonts, scales beautifully. Alternative: Tiempos Headline if licensed. |
| Body | **Inter** (variable) | Clean, highly legible, free. Alternative: Söhne if licensed. |

Avoid: Montserrat, Poppins, Roboto, Lato, Open Sans — these are AI-template tells.

### Type — RE/MAX Collection sub-brand

| Token | Family | Notes |
|---|---|---|
| Display | **Cormorant Garamond** (or Editorial New if licensed) | Higher-contrast, more editorial serif. Reads as the "premium press." |
| Body | **Inter** (kept) | Continuity across the site for body text — only the display register shifts. |

Type scale (Webflow Variables, applies site-wide):

```
text/display-xl    72px / 1.05 / -0.02em      (hero only)
text/display-lg    56px / 1.10 / -0.015em     (page heroes)
text/display-md    40px / 1.15 / -0.01em      (section headlines)
text/heading-lg    30px / 1.20                (subsections)
text/heading-md    22px / 1.30                (card titles)
text/heading-sm    18px / 1.40                (small headings)
text/body-lg       19px / 1.60                (lead paragraphs)
text/body-md       16px / 1.60                (default body)
text/body-sm       14px / 1.50                (captions, meta)
text/eyebrow       12px / 1.40 / 0.08em / uppercase
text/price         32–40px / 1.10 / 500       (property prices, treated like display)
```

### Color — primary brand (RE/MAX-aligned, refined)

```
color/bg/canvas              #FAFAF7   warm near-white default
color/bg/surface             #FFFFFF   cards, panels
color/bg/inverse             #0E1A1F   deep ink — footer, dark bands
color/bg/sand                #ECE4D7   warm tonal accent

color/text/primary           #1A1A1A
color/text/secondary         #5A5A5A
color/text/muted             #8A8A8A
color/text/inverse           #FAFAF7

color/brand/remax-red        #DC1C2E   official RE/MAX red — used selectively
color/brand/remax-blue       #003DA5   official RE/MAX blue — secondary
color/brand/primary          #0F3D4A   deep ocean — site-level primary, replaces red as the dominant brand color
color/brand/secondary        #C9A876   warm sand — accent
color/brand/accent           use brand/remax-red sparingly (pills, "New," "Featured")

color/border/subtle          #E8E5E0
color/border/strong          #1A1A1A

color/status/available       #2E7D5B
color/status/under-offer     #B8843A
color/status/sold            #6E6E6E
color/status/coming-soon     #4A6FA5
```

The RE/MAX red and blue stay present as franchise equity (logo lockup, key CTAs, status pills) but the dominant on-page color is the deep ocean primary. This is how we get the franchise recognition without the visual register sliding into "standard RE/MAX site."

### Color — RE/MAX Collection sub-brand

The Collection experience uses a separately scoped palette applied via a `[data-collection="true"]` body attribute on Collection-flagged pages:

```
color/collection/canvas      #0E1A1F   inverted — Collection runs dark by default
color/collection/surface     #16242A
color/collection/text        #F5F1E8   warm cream
color/collection/accent      #C9A876   warm sand — the "gold" of the Collection
color/collection/divider     #2A3940
```

Collection pages: dark mode by default, serif display in Cormorant Garamond, no RE/MAX red on-page (the RE/MAX Collection wordmark in the navbar shifts to its monochrome treatment), full-bleed photography, longer copy paragraphs, tighter page widths (1280px max).

### Spacing scale (Webflow Variables)

```
space/2xs   4px
space/xs    8px
space/sm    12px
space/md    16px
space/lg    24px
space/xl    40px
space/2xl   64px
space/3xl   96px
space/4xl   128px
```

Section vertical padding: 96px desktop, 64px tablet, 40px mobile. Generous on luxury pages.

### Layout

- Container max-width: 1440px content, 1280px text-heavy, full-bleed for hero galleries.
- Grid: 12-col desktop, 8-col tablet, 4-col mobile.
- Gutter: 24px desktop, 16px mobile.

### Imagery direction

Photography is 70% of how this site feels. See Section 12 / content brief for the full shot list. Direction at a glance: natural light first, golden and blue hour for exteriors, drone for every Collection-tier listing and any property over $1M, lifestyle staging (set the dining table, drape one towel by the pool — empty rooms are sterile), no HDR overcooking, no virtual staging on luxury, no stock-Caribbean palm-and-hammock filler. Real Curaçao texture: Pietermaai pastels at golden hour, Vista Royal salt-pan views, Spanish Water yacht at anchor, Boca Gentil terraces, Coral Estate's coastline, Jan Thiel Beach early morning.

### Motion

- Page load: 300ms fade. No full-screen loaders.
- Scroll reveal: 200ms fade + 12px upward shift, ease-out cubic. Use sparingly.
- Hover: 200ms ease-out. Property card image zoom: 1.03 max.
- Gallery transitions: 300–400ms ease.
- `prefers-reduced-motion` respected — non-essential animation suppressed.

Avoid: parallax everywhere, scroll-jacking, letter-by-letter text animation, particle effects.

---

## 4. Webflow CMS collections and fields

### Properties

**Identity & status**
- Name (Plain text, required)
- Slug (auto)
- Listing reference (Plain text) — internal, e.g. `JT-2026-014`
- Transaction type (Option, required) — For sale / Long-term rental / New development / Commercial / Lot
- Status (Option, required) — Available / Under offer / Sold / Rented / Coming soon / Off-market
- Featured (Switch)
- Featured on Home (Switch)
- Date listed (Date)

**Brand tier (drives sub-brand routing)**
- **Tier** (Option, required) — Standard / **RE/MAX Collection** / **The View** / Off-market
- **Investor property** (Switch) — surfaces in the Investors hub; not the same as Investor permit eligible
- **Investor permit eligible** (Switch) — properties priced ≥ $280K and meeting permit criteria

**Pricing & ownership**
- Price USD (Number) — primary
- Price EUR (Number, optional)
- Price XCG (Number, optional)
- Price display override (Plain text) — for "Price on request" / POA, especially Collection
- **Ownership type** (Option, required) — Eigendom (freehold) / Erfpacht (long lease)
- Erfpacht — annual canon (Number, optional, conditional)
- Erfpacht — years remaining (Number, optional, conditional)

**Location**
- Neighborhood (Reference → Neighborhoods, required)
- Address — display (Plain text) — public approximate, e.g. "Vista Royal, Jan Thiel"
- Address — exact (Plain text, internal-only)
- Map embed URL (Plain text)
- Latitude (Number, optional)
- Longitude (Number, optional)
- Show exact location on map (Switch) — default off

**Specs**
- Bedrooms (Number)
- Bathrooms (Number)
- Interior size m² (Number)
- Lot size m² (Number)
- Year built (Number)
- Property type (Option) — Villa / Apartment / Penthouse / Townhouse / Land / Commercial / Boutique resort / Other

**Feature flags** (booleans, drive filters)
- Ocean view, Waterfront, Pool, Gated community, Furnished, New construction, Solar panels, Mooring / private dock

**Content**
- Short description (Plain text, ~140 chars)
- Full description (Rich text)
- Key features (Rich text)
- Amenities (Rich text)

**Media**
- Main image (Image, required)
- Gallery images (Multi-image, required, min 8)
- Floor plan (Image or File)
- Brochure PDF (File) — gated lead magnet
- Virtual tour URL (Plain text) — Matterport
- Video URL (Plain text) — YouTube/Vimeo

**Relationships**
- Assigned agent (Reference → Agents, required)
- Development (Reference → Developments, optional) — populated for The View units
- Similar properties (Multi-reference, optional)

**SEO**
- SEO title (Plain text)
- SEO description (Plain text)
- Open Graph image (Image, optional)

**Localized fields (EN/NL/ES/DE):** Name, Short description, Full description, Key features, Amenities, Address — display, SEO title, SEO description. Inherited (single source): everything else, including all prices and specs.

### Agents

Name, Role / title, Slug, Photo, Bio (Rich text), Languages spoken (Multi-option: NL/EN/PAP/ES/DE/FR/PT/Other), Email, Phone, WhatsApp number (E.164, e.g. `+5999XXXXXXX`), LinkedIn URL, Specialties — neighborhoods (Multi-ref), Specialties — property types (Multi-option), Years in Curaçao market (Number), FIU compliance officer (Switch — flag for the dedicated compliance officer's profile), Featured (Switch).

### Neighborhoods

Name, Slug, Tier (Option: Tier 1 luxury / Tier 2 historic / Tier 3 family / Tier 4 emerging), Hero image, Short description, Lifestyle description (Rich text), Key highlights (Rich text), Average price text, Map embed URL, Featured (Switch), SEO title, SEO description.

Localized: Short description, Lifestyle description, Key highlights, Average price text, SEO fields.

### Developments (new collection — for new-build projects)

Name (e.g., "The View Resort & Marina"), Slug, Hero image, Hero video URL, Tagline, Long description (Rich text), Total units, Marina specs (Rich text — for The View), Status (Pre-construction / Selling / Sold out), Completion date (Date), Brochure PDF, External marketing URL (e.g., theviewcuracao.com), Assigned lead agent (Reference → Agents).

### Offices

Name (Jan Thiel HQ / Blue Bay / Coral Estate), Slug, Address, Map embed URL, Phone, Hero image, Office hours (Plain text), Lead agents (Multi-reference → Agents).

### Testimonials

Client name OR anonymized label, Client type (Buyer/Seller/Renter/Investor), Quote (Rich text), Rating (1–5), Property type, Related agent, Photo, Date, Featured.

### Insights / Articles

Title, Slug, Author (Reference → Agents), Category (Market reports / Neighborhood spotlights / Buyer's guide / Tax & legal / Investor permit / Lifestyle / News / The View update), Featured image, Excerpt, Body (Rich text), Publish date, Reading time, Related properties, Related neighborhoods, SEO title, SEO description.

### Site settings (singleton)

A single-item collection storing global values the agency can edit without developer help:
- WhatsApp number (E.164)
- USD → EUR conversion rate
- USD → XCG conversion rate
- Default mortgage rate %
- Default down-payment % (resident / non-resident split)
- Default lodging tax %
- Footer disclaimer text
- Cookie banner copy
- Featured Insights (Multi-reference)

---

## 5. Reusable components (Webflow Components — not Symbols)

| Component | Purpose / variants |
|---|---|
| **Navbar** | Variants: transparent (over hero), solid (default scrolled), inverted (Collection dark pages). Includes language switcher (EN/NL/ES/DE), currency toggle (USD/EUR/XCG), top-level nav, global search, contact CTA. |
| **Footer** | Three offices, quick links, language switcher, currency toggle, newsletter signup, legal links, social, FIU compliance badge. |
| **Property Card** | CMS-bound. Variants: Standard / Collection (dark, larger image, less chrome) / The View unit / Compact (used in similar-properties rails). |
| **Agent Card** | Photo, name, role, languages spoken (chips), WhatsApp + email, "Speak with [name]" CTA. |
| **Neighborhood Card** | Hero image, name, short description, dynamic "X properties available" count, Tier chip. |
| **CTA Band** | Variants: Standard / Split / Image-bg / Quiet / Collection (dark, serif). |
| **Search Filter Bar** | Sticky on listings page (desktop). See Section 8. |
| **Viewing Request Modal** | Triggers from any property card or detail-page CTA. Pre-fills hidden context. |
| **Off-Market Access Form** | Gated CTA on Collection / Off-market pages. |
| **Valuation Request Form** | Sell-with-us page + footer/contact entry points. |
| **WhatsApp Floating Button** | Always visible mobile; desktop appears on listings + property detail. |
| **Newsletter / Buyer Alert Form** | Footer + listings page + neighborhood detail empty state. |
| **Language Switcher** | EN / NL / ES / DE — labels not flags. Cookie-persisted. |
| **Currency Toggle** | USD / EUR / XCG — cookie-persisted, swaps displayed prices site-wide. |
| **Sticky Mobile CTA Bar** | Property detail, mobile only — Schedule viewing + WhatsApp. |
| **Mortgage Calculator** | Custom JS embed; pre-filled with listing price; hides on rentals. |
| **Buyer's Cost (Kosten Koper) Calculator** | Custom JS embed; for-sale only. |
| **Vacation Rental ROI Calculator** | Custom JS embed; lives in Investors hub + investor-flagged listings. |
| **Compliance Trust Strip** | Inline component — "FIU compliant since [year] · RE/MAX since 2006 · Cooperation with Brouwer Taxaties." Used on Home, About, Sell-with-us, Investors. |
| **The View Hero Module** | Cinematic landing block for the Home page promoting The View Resort & Marina. |
| **The Collection Trailer** | Editorial intro band that, on Home, promotes The Collection sub-brand experience. |
| **Office Locator Card** | Used on Contact and About — three offices with map and direct contact. |
| **Insights Card** | Article preview — image, category chip, title, excerpt, reading time. |
| **Compliance Disclaimer Block** | Footer-anchored or inline; canonical text from `legal-and-finance.md`. |
| **Cookie Banner** | LBP / GDPR-aligned; necessary / analytics / marketing categories. |

All reusable components built with named props/slots so the same Property Card renders identically whether it's on Home, Properties, a Neighborhood, or an Agent detail page.

---

## 6. Page-by-page layout

### Home

1. **Hero** — full-bleed cinematic loop (10–15s, muted, autoplay) of Curaçao lifestyle and one or two BonBini properties. Headline (EN draft): *"Curaçao's most-trusted address for buyers who arrive informed."* Subhead: *"Twenty years on the island. The only RE/MAX network in Curaçao. Three offices, twenty-plus advisors, one team that knows what your property is worth."* Embedded search bar with three tabs: **Buy / Rent / Investors**. Buy tab default — fields: neighborhood, price range USD, bedrooms, "Search" button → `/properties/for-sale?{filters}`.
2. **Compliance trust strip** — 4-column stat band: "20 yrs since 2005" · "Global RE/MAX network" · "First FIU-compliant agency in Curaçao" · "3 offices · 20+ advisors."
3. **Featured listings** — CMS grid, 6 cards, filtered to `Featured on Home = true`, sorted by Date listed desc. → `/properties/for-sale`.
4. **The Collection trailer** — full-bleed dark band with serif headline ("*The RE/MAX Collection — Curaçao's most discreet portfolio*"), one cinematic Collection image, one short paragraph, single CTA → `/the-collection`.
5. **The View Resort & Marina hero module** — full-bleed module (split or full-width) showcasing The View. Headline + subhead + key facts (120 units, private marina, Zakitó Lagoon) + dual CTA: "Explore The View" → `/developments/the-view-resort-marina`, "Download brochure" → gated PDF lead-capture.
6. **Why Curaçao** — 3-column block. Selected pillars (in order): *Outside the hurricane belt* / *Dutch legal certainty* / *No foreign-ownership restrictions, capital gains tax 0*. Each with a one-line proof and a "Read more" → `/buying/why-curacao`.
7. **Featured neighborhoods** — 4 neighborhood cards (CMS, `Featured = true`): Jan Thiel / Vista Royal, Blue Bay, Coral Estate, Jan Sofat. → `/neighborhoods/{slug}`.
8. **For sellers band** — Quiet CTA Band. Headline: *"Considering a sale? We bring real buyers to the table — and we bring data."* Subhead references Brouwer Taxaties cooperation. Primary CTA → `/selling/sell-with-us`. Secondary CTA → "Request a confidential valuation" (modal).
9. **Investors band** — split-image CTA. Headline: *"Curaçao real estate as an investment, with the structures and yields explained."* CTA → `/investors`.
10. **Insights snapshot** — latest 3 articles, CMS-driven, sorted by Publish date desc. → `/insights`.
11. **Testimonials** — anonymized-by-default carousel (3 visible desktop, 1 mobile). Filter: `Featured = true`.
12. **Final CTA band** — three-up: *Speak with an advisor* (modal) / *WhatsApp us* (deeplink) / *Request valuation* (modal).
13. **Footer**.

### Properties — For sale (listings page)

1. Page hero — short, category-specific. Headline: *"Properties for sale in Curaçao."* Subhead: 1 line + result count.
2. Sticky search & filter bar — see Section 8.
3. Active filter chips, "Clear all" link.
4. Results count: *"Showing X of Y properties."*
5. Sort dropdown — Newest / Price low → high / Price high → low / Largest interior / Largest lot.
6. CMS grid — 3-col desktop, 2-col tablet, 1-col mobile. Pagination at 24 per page or infinite-scroll (Finsweet).
7. Empty state — *"No properties match your filters right now. Tell us what you're looking for and we'll search privately for you."* → off-market access form.
8. Buyer alert signup — full-width band below grid.
9. Final CTA band — Speak with an advisor / WhatsApp.
10. Footer.

The same template is used for `/properties/for-rent`, `/properties/commercial`, and `/properties/lots`, with the page hero copy and default Transaction-type filter swapped per route.

### Properties — The RE/MAX Collection

A separate, more editorial template — Collection sub-brand styling applies (dark canvas, serif display, generous whitespace).

1. Hero — full-bleed cinematic image. Headline: *"The RE/MAX Collection."* Subhead: *"Curaçao's most exceptional homes. Some are listed publicly. Others are not."*
2. Editorial intro — 2 paragraphs framing what The Collection is, the discretion threshold, the expectation of off-market activity.
3. Public Collection grid — CMS, filtered to `Tier = RE/MAX Collection AND Status ≠ Off-market`. Larger card variant, 2-col desktop.
4. Off-market gateway — full-bleed band. Headline: *"Some of our most significant addresses never appear here."* CTA: "Request off-market access" → off-market access form (gated).
5. The Collection promise — 4-up: *Discretion* / *Curated network* / *Pricing precision (Brouwer Taxaties cooperation)* / *Global RE/MAX Collection reach*.
6. Featured Collection neighborhoods — Jan Sofat, Boca Gentil, Coral Estate, Santa Barbara Plantation, Vista Royal.
7. Final CTA — split: *Speak with a Collection advisor* / *Request off-market access*.

### Property detail (CMS template)

Single template, behavior driven by Tier and Transaction type fields.

1. **Gallery hero** — full-width gallery; status badge (top-left); transaction-type chip (top-right); price overlay. Collection-tier listings get a darker gallery treatment and serif overlay.
2. **Sticky info bar** (desktop) — bedrooms / bathrooms / interior m² / lot m² / ownership type / listing reference. Becomes sticky mobile CTA bar on mobile.
3. **Key facts** — full grid: Bedrooms, Bathrooms, Interior, Lot, Year built, Ownership (Eigendom/Erfpacht — clearly labelled), Property type, Listing reference, Neighborhood (linked).
4. **Overview** — 2–4 paragraphs from `Full description`, agency-written.
5. **Features** — bulleted, from `Key features` rich text.
6. **Amenities** — bulleted, from `Amenities` rich text.
7. **Floor plan** — image or PDF download, conditional on field populated.
8. **Virtual tour** — Matterport embed, conditional.
9. **Video** — drone or walkthrough, conditional.
10. **Map / location** — Google Maps embed; default neighborhood-area pin with disclaimer *"Approximate location. Exact address shared after viewing request."* For listings where `Show exact location on map = true`, exact pin with no disclaimer.
11. **Mortgage calculator** — for-sale and new-development listings only. Pre-filled with this listing's price USD. Disclaimer block beneath. Lead-capture variant: "Email me this scenario."
12. **Buyer's costs (kosten koper) explainer** — for-sale only. Inline breakdown: 4% transfer tax · ~1.75% notary · ~$510 land registry · mortgage costs if applicable. CTA → "Calculate full buyer's costs" (Buyer's Cost Calculator component).
13. **Vacation rental ROI snapshot** — appears only on listings with `Investor property = true`. Shows estimated gross yield, occupancy assumption, lodging-tax handling.
14. **Viewing request form** — primary on-page CTA. Hidden context: property name, listing reference, URL, assigned agent email, locale.
15. **Agent card** — assigned agent. Photo, name, role, languages, WhatsApp + email + "Speak with [name]" → modal pre-filled with property context.
16. **Similar properties** — 3 CMS-filtered: same neighborhood OR price ±20% AND same bedroom count, excluding this listing.
17. **Sticky mobile CTA bar** — Schedule viewing / WhatsApp.

### New developments — The View Resort & Marina (hand-built landing)

This is the featured project module promised in the brief. It lives at `/developments/the-view-resort-marina` on the main domain while `theviewcuracao.com` continues as a marketing landing (a clear "Visit the project site" link is included).

1. Cinematic hero — full-bleed video loop. Headline: *"The View Resort & Marina."* Subhead: *"120 luxury residences and a private marina at Zakitó Lagoon. Sold exclusively by RE/MAX BonBini Curaçao."*
2. Project at a glance — 4-up stat band: 120 residences · Private marina · Zakitó Lagoon · Sold exclusively by BonBini.
3. The vision — 2-paragraph editorial intro + cinematic image.
4. Architecture & residences — gallery + key spec list.
5. The marina — dedicated section with marina specs (slips, max yacht length, services).
6. Location — map of Zakitó Lagoon position + lifestyle context (proximity to Pietermaai, Punda, Jan Thiel).
7. Available residences — CMS grid filtered to `Development = The View AND Status = Available`. Card variant: "The View unit."
8. Investor opportunity — yield model + investor-permit eligibility note + CTA.
9. Project timeline — completion phases.
10. Brochure download — gated; lead-capture form returns the PDF.
11. Schedule a private viewing — viewing-request form pre-filled with `Development = The View`.
12. Visit the marketing site — outbound link to theviewcuracao.com (open in new tab, `rel="noopener"`, GA4 outbound event tracked).

### Neighborhoods index

1. Hero — short editorial framing of Curaçao's neighborhood diversity.
2. Tier 1 grid — Featured neighborhoods (Jan Thiel/Vista Royal, Blue Bay, Coral Estate, Jan Sofat, Boca Gentil, Santa Barbara Plantation, Pietermaai).
3. Tier 2 grid — Historic / urban (Pietermaai, Punda, Otrobanda, Scharloo).
4. Tier 3 grid — Family / practical (Mahaai, Damacor, Toni Kunchi, Zuurzak).
5. Tier 4 grid — Emerging (Westpunt, Hofi St. Joris).
6. CTA band — *"Not sure which area fits? Speak with an advisor."*

### Neighborhood detail (CMS template)

1. Hero — `Hero image`, neighborhood `Name`, Tier chip.
2. Lifestyle description — `Lifestyle description` rich text, 2-col layout with inline imagery.
3. Key highlights — bulleted from `Key highlights`.
4. Average price text — `Average price text` (when populated).
5. Map embed.
6. **Properties available in [Neighborhood]** — CMS grid filtered to this neighborhood, `Status = Available`.
7. Local insights — Insights articles where `Related neighborhoods` includes this neighborhood.
8. CTA: *"Speak with our [Neighborhood] specialist"* — pre-filled with the neighborhood and routed to a neighborhood-specialist agent (manually mapped via Site Settings or Agent specialty fields).

### Sell with us

1. Seller-focused hero — *"Confidential, accurate valuations from the team that's sold more property in Curaçao than anyone else."* Subhead references 20 years and Brouwer Taxaties cooperation.
2. **Valuation request form** — primary CTA above the fold.
3. Process — 6-step visual timeline: consult → value (with Brouwer data) → prepare → market (RE/MAX global network) → negotiate → close.
4. Marketing package — what BonBini does for sellers: photography (drone, twilight), video walkthroughs, copy in EN/NL/ES/DE, RE/MAX global portal listings, social ads, buyer-database outreach, FIU-compliant transactions.
5. Recent sales — anonymized track record. Cards: *"Villa, Vista Royal, sold 47 days, 98% of asking."*
6. Testimonials — sellers-only filter.
7. CTA — *"Request a confidential valuation."*

### Buying guide (long-form hub)

Anchored long-form page or hub:
- Why Curaçao
- Eigendom vs. erfpacht (full primer)
- The buying process step-by-step (offer → 3-day cooling-off → 10% notary escrow → Kadaster due diligence (note current ~3-month notary timeline) → transport act → keys)
- Buyer's costs (kosten koper) detailed breakdown
- Mortgages — residents vs. non-residents, current 4.5–6% rate range, named banks
- Investor permit pathway
- AML / identity verification expectation
- FAQ — 15–20 questions
- CTA: *"Speak with an advisor"* + downloadable PDF *"BonBini Buyer's Guide"* (lead magnet).

### Investors hub

1. Hero — *"Curaçao real estate, as an investment."*
2. The investment thesis — 4-up: capital gains 0% on private residence sales · 7%/6%/0% lodging tax structure · 14%-range gross yields · investor-permit ladder.
3. Vacation rental ROI calculator — interactive embed.
4. Investor permit pathway — 3-tier table ($280K / $425K / $850K) with citizenship-pathway note.
5. SPF / holding structures — informational primer with explicit "consult a Curaçao tax advisor" framing.
6. Featured investor properties — CMS grid, `Investor property = true`, sorted by `Date listed`.
7. Insights — articles tagged `Category = Investor permit` or `Tax & legal`.
8. CTA — *"Speak with an investment advisor"* — routed to a designated investor-specialist agent.

### About BonBini

1. Story — founded 2005, RE/MAX franchise 2006, ownership transition 2024 (Vervoord/Houtsma).
2. Compliance commitment — first Curaçao agency fully FIU-compliant; what that means for the buyer.
3. The leadership team — named profiles: Nick Vervoord, Joost Houtsma, Chris Vervoord, Thom Vervoord.
4. Agents grid — CMS, all agents, filterable by language and neighborhood specialty.
5. The three offices — Eden Mall (Caracasbaaiweg 280, Jan Thiel) / Blue Bay Golf & Beach Resort / Coral Estate Resort. Each with map, photo, hours, lead agents.
6. Cooperation with Brouwer Taxaties — short editorial block.
7. Global RE/MAX network — what it means for buyer reach.
8. CTA — Speak with our team.

### Agent detail (CMS template)

Photo, role, bio, languages spoken (chips), specialties (neighborhoods + property types), years in market, FIU compliance officer flag if applicable, contact (email, phone, WhatsApp), featured properties (filtered by `Assigned agent`), testimonials (filtered by `Related agent`), "Speak with [name]" form pre-filled.

### Insights index

CMS index, filterable by Category. 3-column grid desktop. Featured article banner at top. Newsletter signup at bottom.

### Insights article (CMS template)

Editorial layout: cover image, byline (author = agent), reading time, body (rich text with proper typographic rhythm — drop caps optional, pull quotes, image rights), share row, related insights, related properties (where applicable), final CTA band.

### Contact

1. Hero with intent picker — 4-up tile: *I want to buy* / *I want to sell* / *I want to rent* / *I want a valuation*. Each routes to an appropriate form pre-filled.
2. General contact form.
3. WhatsApp button (primary mobile CTA).
4. Three offices grid — name, address, phone, hours, map embed, lead agent.
5. Direct agent contact grid — opt to message any agent directly.
6. FIU compliance & data protection mention with link to privacy policy.

### Legal pages

Privacy policy (LBP / EU-aligned, GDPR-style data subject rights), Cookie notice, Terms, Disclaimer. Standard structure, plain language.

---

## 7. Button and form behavior

### Buttons (every CTA, with destination)

**Global / navbar / footer**
- `[Speak with an advisor]` → opens *General Contact* modal
- `[WhatsApp us]` → `https://wa.me/{SiteSettings.WhatsApp}?text={localized General prefill}`
- `[List your property]` → `/selling/sell-with-us`
- `[Request a valuation]` → opens *Valuation Request* modal
- `[Subscribe to property alerts]` → opens *Buyer Alert* modal
- `[EN | NL | ES | DE]` → switches Webflow locale, persists via cookie
- `[USD | EUR | XCG]` → swaps display currency site-wide via JS, persists via cookie

**Home**
- `[Search properties]` (hero) → `/properties/for-sale?neighborhood={x}&price-min={y}&price-max={z}&bedrooms={n}`
- `[Explore featured properties]` → `/properties/for-sale`
- `[Discover The Collection]` → `/the-collection`
- `[Explore The View]` → `/developments/the-view-resort-marina`
- `[Download The View brochure]` → gated form → returns PDF
- `[Read more — Why Curaçao]` → `/buying/why-curacao`
- `[Request a confidential valuation]` → opens *Valuation Request* modal
- `[Speak with an investment advisor]` → opens *General Contact* modal pre-filled with intent = Investor

**Properties listing**
- `[Filter & sort]` (mobile) → opens full-screen filter modal
- `[Clear all]` → resets all filter chips
- `[More filters]` → opens filter drawer
- `[Tell us what you're looking for]` (empty state) → opens *Off-Market Access* modal
- Property card whole-card click → `/properties/{slug}`
- Card WhatsApp icon → `https://wa.me/{number}?text=Hello, I'm interested in {Property Name} — {Property URL}. Could you share more information?`

**Property detail**
- `[Schedule a private viewing]` (primary) → opens *Viewing Request* modal pre-filled with property context
- `[WhatsApp us about this property]` → `https://wa.me/{SiteSettings.WhatsApp}?text={localized property prefill}`
- `[Download brochure]` → gated *Brochure Download* form → returns PDF
- `[Email me this scenario]` (mortgage calc) → opens lead-capture modal with calc values as hidden context
- `[Calculate full buyer's costs]` → scrolls to / opens Buyer's Cost Calculator embed
- Sticky mobile CTA bar: `[Viewing]` / `[WhatsApp]`

**The Collection**
- `[Request off-market access]` → opens *Off-Market Access* modal (gated, requires confirmed buyer status)
- `[Speak with a Collection advisor]` → opens *General Contact* modal routed to Collection-tier agents

**The View**
- `[Schedule a private viewing]` → *Viewing Request* modal pre-filled `Development = The View`
- `[Download brochure]` → gated brochure form
- `[Visit theviewcuracao.com]` → external new tab + GA4 `outbound_click` event

**Sell with us**
- `[Request a confidential valuation]` → opens *Valuation Request* modal

### Forms (full spec for each)

#### Viewing request form

Fields: First name *, Last name *, Email *, Phone (with country code) *, Preferred contact method (Email/Phone/WhatsApp) *, Preferred viewing date, Preferred viewing time (Morning/Afternoon/Evening/Flexible), Buyer status (Just exploring/Active buyer/Pre-approved/Cash buyer), Message.

Hidden: Property name, Listing reference, Property URL, Assigned agent email, Locale, UTMs, Page URL.

Validation: HTML5 email + tel patterns; custom messages per field.

LBP consent checkbox (required, unchecked default): *"I agree to be contacted about this enquiry. See our privacy policy."*

Success state: in-page swap to *"Thank you. A property advisor will confirm availability and viewing options shortly."* + secondary CTA "While we get back to you — explore similar properties in [Neighborhood]" linking to filtered listings.

Notification routing (Webflow Logic):
- Email to assigned agent (from hidden field)
- Email to compliance officer for audit log
- Webhook to CRM (HubSpot or Pipedrive depending on which agency runs)
- If `Buyer status = Cash buyer` OR `Pre-approved` → Slack alert to leadership inbox

#### Valuation request form

Fields: Name *, Email *, Phone *, Property address or area *, Property type *, Bedrooms, Bathrooms, Estimated interior m², Estimated lot m², Year built, Selling timeframe (ASAP / 1–3 mo / 3–6 mo / Just exploring) *, Preferred contact method *, Message.

Hidden: Page URL, Locale, UTMs.

Consent: required.

Success: *"Thank you. We will review your details and contact you for a confidential valuation within one business day."* Follow-up CTA: "Read about our seller marketing package" → `/selling/marketing-package`.

Routing: route to listing-side lead agent for the named neighborhood (mapped via Site Settings) + leadership inbox.

#### Buyer alert form

Fields: Name *, Email *, Phone or WhatsApp, Buy/Rent/Either *, Preferred neighborhoods (multi-select), Budget range *, Property type, Bedrooms (min), Must-have features (multi: Ocean view/Pool/Waterfront/Gated/etc.), Investor permit interest (Y/N).

Consent: required. Double opt-in via confirmation email (LBP best practice).

Success: *"You're on the list. We'll send matching properties — including off-market opportunities — when they become available."*

Routing: webhook to email platform (Brevo/Mailchimp/ActiveCampaign) into a tagged segment.

#### Off-market access form

Fields: Name *, Email *, Phone *, Confirmed buyer status (Just exploring / Active / Pre-approved / Cash buyer) *, Budget range *, Preferred neighborhoods, Message.

Consent: required.

Success: *"Thank you. Off-market opportunities are shared selectively. An advisor will reach out to verify your search."*

Routing: route only to designated Collection / off-market lead agents (small named subset), plus compliance officer for audit. Slack alert to leadership.

#### Brochure download form

Fields: Name *, Email *, Property/development reference (hidden, pre-filled).

Consent: required.

Success: in-page download trigger + email confirmation with PDF attached.

Routing: webhook to email platform with brochure-tag segmentation; lead routed to listing's assigned agent.

#### Mortgage scenario lead-capture (calculator)

Fields: Name *, Email *.

Hidden: Property name, calculator inputs (price, down payment, rate, term).

Success: *"Sent. You'll have the scenario in your inbox in a moment."*

Routing: emailed to user; copy to assigned agent.

#### Newsletter signup (footer)

Fields: Email *, Locale (auto).
Double opt-in.
Success: *"Confirmation sent — please check your inbox."*

#### General contact (intent-based)

Two-step: intent picker (Buy/Sell/Rent/Valuation/Investor/Other), then dynamic fields based on intent. Drives lead routing.

---

## 8. Search, filtering, and CMS logic

### Tool

**Finsweet Attributes (CMS Filter, CMS Combine, CMS Load)** — default. Free, no-code, robust at this CMS scale (~165 properties + rentals + commercial + lots = ~250–300 items).

Alternative noted but not chosen: Jetboost (paid, easier visual setup) — recommend only if the agency wants a hosted dashboard.

### Filter set

| Filter | CMS field | Behavior |
|---|---|---|
| Transaction type | `Transaction type` | Tabs at top of bar — For sale / Long-term rental / New development / Commercial / Lot |
| Location | `Neighborhood` (reference) | Multi-select; populated from Neighborhoods CMS |
| Property type | `Property type` | Multi-select |
| Price range | `Price USD` | Slider + min/max input (USD primary, currency-toggle aware) |
| Bedrooms | `Bedrooms` | 1 / 2 / 3 / 4 / 5+ buttons |
| Bathrooms | `Bathrooms` | 1 / 2 / 3 / 4+ buttons |
| Interior m² | `Interior size m²` | Range |
| Lot m² | `Lot size m²` | Range |
| **Ownership type** | `Ownership type` | Eigendom / Erfpacht — first-class filter, Curaçao-specific |
| Status | `Status` | Default visible: Available + Coming soon. Toggle to include Under offer. Sold/Rented archived. |
| Features | `Ocean view`, `Waterfront`, `Pool`, `Gated community`, `Furnished`, `New construction`, `Solar panels`, `Mooring/dock` | Multi-select boolean |
| Investor permit eligible | `Investor permit eligible` | Toggle |
| Tier | `Tier` | Optional advanced filter; Collection-only checkbox surfaces from this |

### Search input

Live-filtered, queries: `Name`, `Listing reference`, `Address — display`, `Neighborhood.Name`. 200ms debounce. Empty state copy: *"No matching properties. Tell us what you're looking for and we'll search privately."* → off-market access form.

### Sort

Newest (default, `Date listed` desc), Price low → high, Price high → low, Largest interior, Largest lot.

### URL state

All filters reflected in querystring (`?neighborhood=jan-thiel&price-min=500000&beds=3`) so search results are linkable, shareable, and SEO-indexable.

### Filter-bar UX

- **Compact bar** (sticky desktop): tabs + neighborhood + price + bedrooms + "More filters" expander.
- **Expanded panel**: drawer on desktop, full-screen modal on mobile.
- **Active chips** below the bar; one-click remove; "Clear all" link.
- **Mobile**: collapses into a single "Filter & sort" button → full-screen filter modal.

### Results behavior

- 24 per page; "Load more" button (Finsweet CMS Load).
- Skeleton-screen loading states (200–300ms).
- 200ms ease-out transition between filter applications (not jarring).

---

## 9. Multilingual setup

### Locales

| Locale | Role | URL pattern |
|---|---|---|
| **EN** | Primary (default) | `/` |
| **NL** | Secondary | `/nl/` |
| **ES** | Tertiary | `/es/` |
| **DE** | Tertiary | `/de/` |

Webflow native **Localization Advanced** for all four locales (~$29/mo per non-primary locale = ~$87/mo at the platform level, absorbed in subscription).

### Auto-routing

Webflow's browser-language detection routes new visitors to their preferred locale on first load; manual switch via the language switcher overrides and persists via cookie.

### What gets localized

**Static page copy:** all of it — headlines, body, CTAs, microcopy, error messages, success states, form labels, navigation.

**CMS field-level localization (per the Properties collection):**
- Properties: Name, Short description, Full description, Key features, Amenities, Address — display, SEO title, SEO description.
- Neighborhoods: Short description, Lifestyle description, Key highlights, Average price text, SEO fields.
- Insights: Title, Excerpt, Body, SEO fields.
- Agents: Bio (only — names/roles inherited from EN).
- Developments: Tagline, Long description, SEO fields.

**Open Graph titles and descriptions** are localized.

### What is inherited (single source of truth, never localized separately)

- All numeric specs (prices, m², bedrooms, bathrooms, year built).
- Coordinates and map embeds.
- Image assets (alt text the only exception, only if the agency wants per-locale alt text).
- Listing reference, slug (kept EN for v1 to reduce setup overhead — can be revisited at v2).

### WhatsApp prefills — localized per locale

| Locale | General prefill |
|---|---|
| EN | "Hello, I'd like to speak with a property advisor about Curaçao real estate." |
| NL | "Hallo, ik zou graag een vastgoedadviseur willen spreken over onroerend goed op Curaçao." |
| ES | "Hola, me gustaría hablar con un asesor inmobiliario sobre bienes raíces en Curazao." |
| DE | "Hallo, ich möchte mit einem Immobilienberater über Immobilien auf Curaçao sprechen." |

Property-specific prefills follow the same pattern with property name and URL injected.

### SEO / hreflang

- Webflow auto-generates `hreflang` alternate tags per locale.
- Canonical URLs per locale.
- Locale-specific `og:locale` tags (`en_US`, `nl_NL`, `es_ES`, `de_DE`).
- Sitemap split per locale.
- Localized SEO titles and descriptions on every page.

### Translation workflow

EN copy written by the agency content team (or my agency under retainer). NL, ES, DE translations: professional human translation passes (Lokalise or direct translator, NOT machine translation alone). Translation memory maintained per agency; new listings translated within the standard "8 listings/month" retainer ceiling for all locales.

### Language switcher

Top-right of the navbar. Labels (`EN / NL / ES / DE`), not flags. Same component on mobile inside the menu drawer.

---

## 10. Responsive behavior

### Desktop (≥ 1280px)

- Spacious layout, large imagery, refined typography.
- Sticky filter bar on listings page.
- 3-col property grid (option of 4 for very dense states).
- Property detail: gallery left, sticky info card right (price + key facts + CTAs) — except Collection template which uses a wider gallery and a less-chromed sticky card.
- Custom hover cursor on property cards (label *"View"*).

### Tablet (768–1279px)

- 2-col property grid.
- Filter bar collapses partially; "More filters" opens a drawer.
- Property detail: gallery full-width; info card stacks below.
- Navbar: condensed nav with "Menu" toggle for secondary items.

### Mobile (< 768px)

- 1-col property grid.
- Filter bar → "Filter & sort" button → full-screen modal.
- Property detail: gallery first (swipeable, image counter), sticky bottom CTA bar (Schedule viewing + WhatsApp).
- WhatsApp floating button always visible, sized not to obstruct content.
- Hamburger menu for nav; language switcher inside menu.

### Sticky CTAs

- Property detail mobile: Schedule viewing + WhatsApp persistent at bottom.
- Properties listing desktop: filter bar persistent at top after scroll past hero.

### Image strategy

Webflow image processor handles responsive variants. Hero images at 2560px wide minimum. WebP delivery with JPG fallback. Lazy-loading on everything below the fold.

---

## 11. SEO, conversion, and analytics

### Title / meta strategy per template

**Home (per locale):**
`[EN]` *RE/MAX BonBini Curaçao — Buy, Sell, and Invest in Curaçao Real Estate*
`[NL]` *RE/MAX BonBini Curaçao — Huizen Kopen, Verkopen en Beleggen op Curaçao*
`[ES]` *RE/MAX BonBini Curazao — Comprar, Vender e Invertir en Curazao*
`[DE]` *RE/MAX BonBini Curaçao — Immobilien Kaufen, Verkaufen und Investieren auf Curaçao*

**Properties listing:** `Properties for {transactionType} in Curaçao | RE/MAX BonBini`

**Property detail:** `{Property Name} — {Property type} for {transactionType} in {Neighborhood} | RE/MAX BonBini`

**Neighborhood detail:** `{Neighborhood} Real Estate — Properties for Sale and Rent | RE/MAX BonBini Curaçao`

**Insights article:** `{Title} — Curaçao Real Estate Insights | RE/MAX BonBini`

**Meta description templates:** 150–160 chars per page, written per page (not auto-generated except for property and neighborhood detail, which use a templated pattern with safe-guards for length).

### Schema.org / JSON-LD

- **Home:** `RealEstateAgent` schema with `name`, `url`, three `address` blocks (the three offices), `telephone`, `priceRange`, `areaServed`, `aggregateRating` if testimonials structured.
- **Property detail:** `RealEstateListing` (or `Product` + `Offer` for stricter validation) — `name`, `description`, `image`, `offers.price` (USD), `offers.priceCurrency`, `address`, `numberOfBedrooms`, `numberOfBathroomsTotal`, `floorSize`, `lotSize`, `yearBuilt`. Also `BreadcrumbList`.
- **Neighborhood detail:** `Place` schema with `geo` coordinates and `description`.
- **Agents:** `Person` schema per agent — `name`, `jobTitle`, `worksFor` (RE/MAX BonBini), `knowsLanguage`, `telephone`, `email`.
- **Insights article:** `Article` schema with `author`, `datePublished`, `dateModified`, `image`, `publisher`.
- **About:** `Organization` schema with `foundingDate` (2005), `founder`, `numberOfEmployees`, `address` (three locations).
- **FAQ pages (Buying guide, Investor permit):** `FAQPage` schema for AEO surfacing.

### GA4 events

Track:
- `view_property_detail` — params: property_id, property_name, neighborhood, price_usd, transaction_type, tier, locale.
- `apply_filter` — params: filter_field, filter_value.
- `viewing_request_submitted` — params: property_id, locale, agent_id, buyer_status.
- `valuation_request_submitted` — params: locale, neighborhood, timeframe.
- `buyer_alert_submitted` — params: budget_range, neighborhoods, locale.
- `off_market_access_submitted` — params: confirmed_buyer_status, budget_range.
- `brochure_download` — params: property_id OR development_id.
- `whatsapp_click` — params: source (footer/floating/property_card/property_detail), property_id (if applicable).
- `language_switch` — params: from_locale, to_locale.
- `currency_switch` — params: from_currency, to_currency.
- `mortgage_scenario_emailed` — params: property_id, calc_inputs.
- `outbound_click` — for theviewcuracao.com.

### Meta Pixel

Standard events: `Lead` (any form submission), `Contact` (WhatsApp click + general contact form), `ViewContent` (property detail view), `CompleteRegistration` (newsletter / buyer alert opt-in).

### Conversion definitions (for the monthly report)

Lead = any of: Viewing request, Valuation request, Off-market access, Buyer alert opt-in, Brochure download with valid email, Mortgage scenario emailed.

Qualified lead (per agency definition, set during onboarding) — likely: pre-approved or cash buyer, or budget ≥ $500K, or Collection-tier interest, or investor-permit interest.

### AEO (Answer Engine Optimization)

For visibility in ChatGPT / Perplexity / Google AI Overviews:

- Comprehensive FAQ schema on Buying Guide, Investor permit page, Eigendom vs. erfpacht page, Kosten koper page.
- Structured data on every property (`RealEstateListing`).
- High-quality, well-structured content covering the questions Curaçao buyers ask: *"Can foreigners buy property in Curaçao?"*, *"What is the investor permit?"*, *"What is eigendom?"*, *"How much are buyer's costs in Curaçao?"*, *"What are mortgage rates in Curaçao?"*.
- `Speakable` schema (`schema.org/SpeakableSpecification`) on the FAQ sections.
- Maintain a clean robots.txt and sitemap; ensure GPTBot, ClaudeBot, PerplexityBot are not blocked (they aren't by default).
- Quarterly content reviews to check for ranking and AI-overview citations.

### Page speed targets

- LCP mobile < 2.5s by month 6, < 2.0s by month 12.
- CLS < 0.1.
- INP < 200ms.

Hosting on Webflow CDN; image optimization on; lazy-loading; minimal JS embeds (only the calculators and the currency toggle).

### Search Console

Verified per locale (one property per locale) plus a parent property for the apex domain. Sitemaps submitted per locale.

---

## 12. Webflow implementation notes + QA checklist

### Class-naming convention

**Client-First** (Finsweet's convention) for all classes. Format: `section_hero`, `padding-section-large`, `card_property`, `text-style-eyebrow`. Combo classes only for variant overrides. No more than two combo classes per element.

### Variables setup

All design tokens as Webflow Variables organized in three modes:
- **Brand** (default — primary brand register).
- **Collection** (sub-brand — applies on Collection-flagged pages via attribute selector).
- **Dark band** (used selectively for dark CTA bands and footer).

Token namespace convention as per Section 3 (`color/`, `space/`, `text/`).

### Components vs. page-level content

- **Components** (Webflow Components, not legacy Symbols): Navbar, Footer, Property Card, Agent Card, Neighborhood Card, all CTA Bands, all Forms, Calculators, Currency Toggle, Language Switcher, WhatsApp Button, Sticky Mobile CTA Bar, Insights Card, Office Locator Card, Compliance Trust Strip.
- **Page-level**: page heroes, editorial content blocks, hand-built feature sections (e.g., The View landing's project-at-a-glance band).
- **CMS templates**: Property detail, Neighborhood detail, Agent detail, Insights article — components used inside.

### Third-party integrations

| Tool | Purpose | Notes |
|---|---|---|
| Finsweet Attributes | CMS filter/search/load on Properties listings | Free; no-code |
| Cookiebot or Webflow native cookie banner | LBP / GDPR-aligned consent | Required |
| Mortgage calculator | Custom JS embed (~50 lines) | See Section 4 of skill ref |
| Buyer's cost calculator | Custom JS embed | Curaçao-specific math |
| Vacation rental ROI calculator | Custom JS embed | Investors hub |
| Currency toggle | Custom JS embed using `Intl.NumberFormat`; rates pulled from Site Settings singleton | Cookie-persisted |
| Google Maps embeds | Per-listing + per-neighborhood + per-office | Static API key, embed only |
| GA4 + Meta Pixel | Analytics + paid-channel tracking | Via Webflow custom code per page |
| Webflow Logic | Form routing (agent assignment, leadership alerts, compliance audit) | Native — preferred over Zapier where it suffices |
| Brevo / Mailchimp / ActiveCampaign | Newsletter + buyer alerts | Webhook from Webflow |
| Pipedrive or HubSpot CRM | Lead pipeline | Webhook (Webflow Logic → CRM API) |
| Slack | Leadership alerts on cash-buyer / pre-approved / off-market leads | Webflow Logic → Slack incoming webhook |
| Hotjar or Microsoft Clarity | Heatmaps + session recording | Quarterly review |
| Google Search Console | SEO monitoring | Per locale |
| Lokalise (or equivalent) | Translation memory & NL/ES/DE workflow | Optional — manual workflow viable for v1 |

### Pre-launch QA checklist

**CMS & content**
- [ ] All Properties have: Name, Listing reference, Transaction type, Status, Price USD, Ownership type, Neighborhood, Bedrooms, Bathrooms, Interior m², Lot m², Main image, ≥8 Gallery images, Assigned agent, SEO title, SEO description.
- [ ] All Neighborhoods have hero, Tier, Lifestyle description, Map embed, SEO fields.
- [ ] All Agents have photo, languages, WhatsApp number in E.164 format, email.
- [ ] Site Settings singleton populated: WhatsApp number, currency rates, mortgage defaults.
- [ ] The View development entry complete with hero video, brochure PDF, lead-agent assignment.

**Components & design**
- [ ] Property card renders correctly across Standard / Collection / The View / Compact variants.
- [ ] Navbar variants (transparent / solid / inverted / Collection) all behave correctly.
- [ ] Sticky mobile CTA bar appears only on property detail mobile.
- [ ] Sticky filter bar works on Properties pages desktop.
- [ ] All calculators render with locale-correct currency formatting.

**Filtering & search**
- [ ] All filters work on Properties listing.
- [ ] Eigendom/Erfpacht filter is first-class.
- [ ] URL state reflects all active filters.
- [ ] Empty state CTA routes to Off-Market Access.
- [ ] Sort dropdown works for all options.

**Multilingual**
- [ ] All four locales accessible via `/`, `/nl/`, `/es/`, `/de/`.
- [ ] Language switcher persists choice via cookie.
- [ ] Auto browser-language routing works on first visit.
- [ ] All static copy localized (no English fallback strings visible in NL/ES/DE).
- [ ] All featured CMS content localized (properties, neighborhoods, insights).
- [ ] hreflang tags present on every page.
- [ ] WhatsApp prefills are localized per locale.
- [ ] OG titles/descriptions localized.

**Forms**
- [ ] Every form has LBP consent checkbox, unchecked by default, required.
- [ ] Hidden context fields populated correctly (property name, ID, URL, locale, UTMs, agent email).
- [ ] Success states display correctly without page reload (or redirect to /thank-you for paid-tracking pages).
- [ ] Error states display correctly with inline messages.
- [ ] Webflow Logic routes leads to correct agents.
- [ ] Off-market form routes only to designated Collection lead agents.
- [ ] Cash-buyer / pre-approved leads trigger Slack alert.
- [ ] Newsletter / buyer alert double opt-in functional.

**Currency toggle**
- [ ] USD / EUR / XCG toggle swaps prices site-wide.
- [ ] Conversion rates pull from Site Settings singleton.
- [ ] Choice persists via cookie.
- [ ] Calculators reflect active currency.

**Analytics & SEO**
- [ ] GA4 firing on all defined events.
- [ ] Meta Pixel installed and firing.
- [ ] Google Search Console verified per locale.
- [ ] JSON-LD schema present and valid (Rich Results Test passing) on Home, Properties listing, Property detail, Neighborhood detail, Agent detail, Insights article, About.
- [ ] Sitemaps submitted per locale.
- [ ] Robots.txt allows GPTBot, ClaudeBot, PerplexityBot, Googlebot.
- [ ] Page-speed LCP < 3.0s on mobile for Home, Property detail, Properties listing (initial target; tightening over months).

**Compliance & legal**
- [ ] Cookie banner shows on first visit, settings savable.
- [ ] Privacy policy + Cookie notice + Terms + Disclaimer pages live.
- [ ] FIU compliance referenced on About + Footer + Compliance Trust Strip.
- [ ] Mortgage calculator includes the canonical Curaçao disclaimer.
- [ ] Buyer's cost calculator includes the canonical disclaimer.
- [ ] Investor permit page includes the canonical immigration disclaimer.
- [ ] Footer carries the standing legal disclaimer.

**Technical**
- [ ] Custom domain DNS + SSL configured for all locales.
- [ ] 301 redirects mapped from realestate-curacao.com legacy URLs to new equivalents (especially property listings — preserve SEO equity).
- [ ] 404 page custom-designed with property suggestions and contact CTA.
- [ ] Print stylesheet on property detail produces a clean print.
- [ ] `prefers-reduced-motion` respected.
- [ ] Keyboard navigation works site-wide (focus states visible).
- [ ] WCAG 2.1 AA color contrast passing on all text/background combinations.
- [ ] All images have alt text (CMS-populated or pattern fallback).

---

## What's covered by your $1,500/month subscription

Build, ongoing listings management (up to 8 new listings/month across the four locales), monthly content publishing (1 article/month + 1 long-form per quarter — neighborhood spotlights, market updates, investor-permit deep-dives, eigendom/erfpacht primers), monthly SEO and performance reporting, conversion iteration (one A/B test or CRO change per quarter), design changes (up to 2 hours/month for new sections, banner refreshes, layout tweaks), technical maintenance (Webflow hosting, CMS management, backups, bug fixes, browser compatibility, platform updates), and 1-business-day email/Slack support with a 30-minute monthly check-in.

**Initial onboarding (months 1–2)** is amortized into the subscription — no separate build fee. Deliverables include this blueprint, the full Webflow build, CMS schema setup, four-locale configuration with Localization Advanced, photography direction, the first 5–15 listings populated, GA4 + Meta Pixel + Search Console configuration, lead routing via Webflow Logic into BonBini's CRM, DNS + SSL + 301 redirect mapping from the legacy site, pre-launch QA, soft launch, public launch.

**KPI targets to set with leadership at signing** (adjustable based on the existing site's baseline):

| Metric | 3-month | 6-month | 12-month |
|---|---|---|---|
| Organic search sessions / mo | 1,500 | 4,000 | 10,000+ |
| Property detail page views / mo | 5,000 | 12,000 | 25,000+ |
| Lead form submissions / mo | 15–25 | 40–60 | 100+ |
| Qualified leads / mo (cash/pre-approved/Collection-tier) | 6–10 | 15–25 | 35+ |
| Avg. time on property detail | 1:45 | 2:15 | 2:30 |
| Bounce rate (listings) | < 55% | < 45% | < 35% |
| Page speed LCP (mobile) | < 3.0s | < 2.5s | < 2.0s |

These targets are higher than the standard agency starting point because BonBini is the market leader entering with an existing audience and existing domain authority — the upgrade should compound, not start from zero.

**What's billed separately** (clear scope guard so the engagement stays clean): drone and twilight property shoots beyond direction, paid Meta/Google ads management, additional locales beyond the launching four (Papiamentu, French, Italian if requested), CRM implementation or migration beyond webhook integration, listings beyond eight per month (priced per-additional at agreed overage rate), and any major mid-engagement redesign.

Monthly performance reports delivered by the 5th of each month, sent by email and reviewed on the standing 30-minute call.
