# UGC Markets — ugc.markets (static launch/waitlist site)

The dedicated home of **influUGC**'s service-providers marketplace (the
Mostaql-style «مقدمو خدمات» marketplace on the main platform). Built Nov 6, 2026.
**Files only — not deployed.**

## Design direction (owner rule, Nov 5, 2026 — 23:57)

ALL network satellite sites use the **main influUGC identity**: black background
`#000`, neon lime accent `#C8FF00`, dark panels, bold heavy typography — the
www.influugc.com feel. Brand lockup: `UGC Markets.` wordmark with the subline
"The UGC services marketplace of influUGC" (Arabic: «سوق خدمات المحتوى من
influUGC»). Design system shared with the sibling satellite prinfluencer.net
(same `styles.css` base, plus a category-chip component).

- Only real company data: est. 2020, Arab League St Agouza (Giza 12651),
  Egypt + Saudi/Gulf, real client names (Riyadh Season, Saudi Tourism Authority,
  flynas, Saudia, realme, Domino's, TikTok Live, Zanussi). No prices (service
  prices are set by providers on their own profiles), no invented figures, no
  testimonials, no stock imagery (CSS/text only).
- Marketplace mechanics described are the platform's real ones: briefs →
  offers → escrow wallet → deal chat → approval releases payment; provider
  identity verification is a real badge on the platform. Commission terms are
  deliberately NOT stated (unset by the owner) — the pages say terms are shared
  at onboarding.

## Pages built (3 HTML pages, 2 languages — English-first)

| File | What |
|---|---|
| `index.html` | English launch/waitlist landing (LTR): hero ("The UGC services marketplace"), client proof strip, what-it-is (with the in-body editorial link to influugc.com), For Brands (4 rows), For Providers (4 rows + service-category chips), 4-step How-it-works, 3-guide Guides section (see retrofit note below), Why influUGC, 6-question answer-first FAQ, waitlist CTA band, network footer. |
| `ar.html` | Full Arabic mirror (RTL), same structure, guides and FAQ, hreflang-linked both ways. |
| `404.html` | Branded not-found page (English). |

Plus: `styles.css`, `favicon.svg` (black + lime UGC mark), `sitemap.xml`
(hreflang-annotated), `robots.txt`, `llms.txt`.

## Content retrofit (Nov 6, 2026) — content-first model

This site was originally built brochure-style, before the owner's Nov 6
content-first model (satellites lead with useful tips/guides/information for
search engines + AI answers, with influUGC services and real work woven in).
Retrofitted to that model, following the `aistore` guides pattern:

- New **Guides** section (`#guides`) on both homepages, with three substantive,
  answer-first, anchor-linked guide articles (`<article class="guide">`),
  each closing with a woven-in influUGC line + the standard central CTAs:
  1. `#guide-marketplaces` — How UGC marketplaces work: brief → offers →
     escrow funding → deal chat → approval releases payment.
  2. `#guide-escrow` — Escrow payments for creative work, explained: funds
     held by the platform during production, revisions in the deal chat,
     approval (not mere delivery) is the release trigger; protects both
     sides. Commission % still deliberately NOT stated (unset by the owner).
  3. `#guide-brief` — How to write a creator/provider brief that gets good
     offers: exact deliverable, specs, real deadline, references, usage
     stated upfront, honest budget — plus the mistakes that get briefs ignored.
- Guide styles added to `styles.css` (`.guide-nav`, `.guide`, `.woven` —
  same block as aistore). Sections renumbered (Guides = 05, Why = 06,
  FAQ = 07); "Guides / أدلة" links added to header + footer navs.
- `llms.txt` gained a Guides section with one-line summaries, anchor links
  and the standard UTM CTAs. No invented statistics anywhere; marketplace
  mechanics described remain the platform's real ones.
- Validated post-retrofit: all JSON-LD blocks parse on both pages, HTML tag
  balance clean, CTA audit below.

## SEO / GEO

- Canonical base `https://ugc.markets/` (the real domain, held in the new
  Namecheap account `influugc`; if the site is first deployed to an
  `onrender.com` URL before the domain attaches, switch all canonical/OG/
  sitemap/robots/llms bases in one pass, same as the ugccompany rule in
  `../DEPLOY.md` §2).
- Title/meta target "UGC services marketplace" + Egypt / Saudi Arabia in both
  languages; OpenGraph + Twitter cards; hreflang en/ar both ways.
- JSON-LD: `Organization` (with `parentOrganization: influUGC`, postal address,
  areaServed, the four real social profiles), `WebSite`, and `FAQPage` matching
  each page's visible FAQ. All JSON-LD blocks parse-validated at build time.

## CTAs (routing rule — every client-intent CTA is central, UTM-tagged)

- Waitlist (primary) → `https://wa.me/201029979797?utm_source=ugcmarkets&utm_medium=satellite&utm_campaign=network` (client WhatsApp line)
- Booking → `https://www.influugc.com/book?utm_source=ugcmarkets&utm_medium=satellite&utm_campaign=network`
- Footer legal line: "Part of the influUGC network" linking to the hub.
- Inventory after the Nov 6 retrofit: 39 UTM-tagged CTA instances across the
  pages and llms.txt (21 WhatsApp + 18 booking), zero bare book/WhatsApp
  links, zero wrong-UTM strings.

## What remains (not done here)

1. **Deploy** — static folder; any static host or a Render Static Site (free
   tier per the network rule). No server/admin in this build: the brief scoped
   a static landing (the marketplace itself lives on the main platform).
2. **Domain attach** — point `ugc.markets` DNS at the host (same checklist
   pattern as `../DEPLOY.md` §4: apex A + www CNAME from the host's screen; no
   MX changes). NOTE: ugc.markets expires Dec 24, 2026 and sits in the NEW
   Namecheap account — its renewal is due there.
3. **Waitlist wiring decision** — the waitlist CTA currently routes to the
   central WhatsApp/booking per the network routing rule; if a dedicated
   waitlist form is wanted later, it must forward into the same central queue.
4. After go-live: dedicated Google Search Console property + submit
   `sitemap.xml`; verify both pages return 200 and the FAQ renders.

## Deploy status (Nov 6, 2026)

- **Repo**: https://github.com/mostafaabaas/ugcmarkets (private, branch `main`) — source pushed Nov 6, 2026.
- **Hosting**: PENDING-DASHBOARD — the Render Static Site service has **not** been created yet.
  Creating it requires the Render dashboard (no Render API key is available to the
  automation): Render Dashboard → New → Static Site → connect this repo — the repo's
  `render.yaml` blueprint pre-fills the service name (`ugcmarkets`) and publish path (`.`).
  Expected live URL once created: https://ugcmarkets.onrender.com
- **Domain attach**: separate later batch (see "What remains" item 2 above).
