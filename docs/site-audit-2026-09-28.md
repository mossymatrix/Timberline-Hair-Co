# Timberline site audit — 2026-09-28

Baseline: `main` at `0d8217456068c5ba23d9987d7a659d8dc7dcd434`. Restore branch: `backup/pre-revamp-2026-09-28`.

## Current setup

- A static, single-page HTML/CSS site served at `https://timberlinehair.com/` by GitHub Pages; `CNAME` points to the domain.
- The public page links directly to the existing GlossGenius booking flow and services. Leave those live while a separate Vagaro trial is evaluated.
- No local forms or analytics code is present in the repository. Domain registrar, DNS, Search Console, Business Profile, and booking account settings cannot be established from repository contents.

## Findings

| Area | Evidence | Next action |
| --- | --- | --- |
| Crawl files | `/robots.txt` and `/sitemap.xml` returned GitHub Pages 404 pages on 2026-09-28. | Add them when the final page URLs are chosen; submit the sitemap in Search Console. |
| Page structure | Only `index.html` exists. Services and stylists are sections; no dedicated About, Contact, or booking page. | Build the checklist's focused pages, with a provider-independent `/book` gateway. |
| Navigation | Desktop links only to Services and About. CSS hides both links below 768px, leaving only the phone number. | Give mobile visitors accessible navigation to services, stylists, contact, and booking. |
| Booking | Three links use `window.open(..., width=600,height=400)` and `target="popup"`. | Replace the popup behavior with ordinary links to the site booking gateway; keep GlossGenius as the public destination until a provider decision. |
| Images | All six displayed images loaded in a desktop browser. Four stylist images use the identical alt text `Stylist Name`; the hero says `Barber`. Source portraits are up to 3.9 MB in the repository. | Write accurate alt text, supply responsive dimensions/lazy loading, and optimize large images without changing the originals until reviewed. |
| Metadata | Homepage has a title, description, social tags, and JSON-LD. No canonical tag; social image uses a relative URL. The meta keywords and copy emphasize barbering while the bios include color services. | Align copy with the agreed service menu, add unique metadata to each new page, and use absolute social-image URLs. |
| Structured data | JSON-LD declares `LocalBusiness`, Tuesday–Saturday hours and a `$20-$50` price range; closed days are represented as midnight-to-midnight opening hours. | Confirm actual business details, then use `HairSalon` and omit closed-day hours; verify price claims before publishing. |
| Accessibility | Stylist images lack distinct descriptions. Services and booking are visually titled with H3 elements directly under the H1, while the team section uses H2. | Use a logical heading outline and meaningful image alternatives. |
| Responsive CSS | Rules exist at 1024, 768, and 480px; no actual phone/tablet device test has been completed. | Test layout, navigation, and booking on phone and tablet before launch. |

## Next work in checklist order

1. Confirm hosting, DNS, analytics/Search Console access, salon details, four stylist details, service menu, and policies with the owners.
2. Build the focused pages in a preview branch while preserving public GlossGenius booking.
3. Add page-specific SEO and local business data after the business facts are verified.
4. Trial Vagaro privately for four stylists, deposits, calendars, and total cost before a public booking change.

This audit is based on the repository and a desktop inspection of the live page. It does not claim verified mobile behavior, DNS ownership, analytics status, or booking/payment behavior.
