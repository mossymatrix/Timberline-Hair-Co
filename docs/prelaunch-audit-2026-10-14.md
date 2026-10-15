# Pre-launch audit — 2026-10-14
Branch: site-revamp. Publication is on hold pending remaining checks.

## Verified in source
- Five public pages each have a unique title, description and HTTPS apex canonical URL; one H1 each.
- Home HairSalon JSON-LD parses and uses the same name, address, telephone and Tue–Sat/Sunday hours as visible site content.
- Public sitemap lists Home, Services, Stylists, Contact and Book only; robots.txt permits crawling and references the sitemap.
- Success page remains noindex, follow and outside the sitemap.
- Prior homepage fragments #services and #about are retained; no removed old page paths were found in the prior main homepage.
- Images have alt attributes and intrinsic dimensions. Hero has loading priority; below-fold portraits/gallery use lazy loading.
- Local page, image, stylesheet and fragment targets resolve in the repository.
- No GlossGenius booking links remain in the six authored pages.

## Fixed in this pass
- Internal links use directory URLs consistent with canonicals rather than index.html.
- Added keyboard skip links, focusable main targets and consistent visible focus indicators.
- Added branded noindex 404.html with service and booking recovery links.
- Button contrast change was reverted at the user's request; original white text and orange hover restored. Preserve the chosen appearance.
- Corrected the homepage introduction's sentence fragment.

## Remaining before publication
- Google Business Profile: verify actual category, business verification status, name/address/phone, regular and special hours, services, and public booking URL. Website source agreement does not establish profile agreement.
- GitHub Pages: confirm publishing source/branch/folder and Enforce HTTPS. Current request to HTTP apex returned HTTP 200 without redirect; HTTPS www redirected to HTTPS apex. Recheck headers and redirects from an independent browser/network.
- Real-browser responsive/accessibility checks (keyboard flow, mobile menu, focus visibility, widget interaction and overflow). Source checks are not browser or screen-reader certification.
- Stylist-specific booking buttons: obtain actual Vagaro provider links before adding. Existing page has a general booking CTA; no provider URLs have been invented.
- Measure booking-page behavior/performance with the third-party widget; field Core Web Vitals require production data.
- Salon test acceptance is recorded, but detailed deposit/refund/cancellation and test-cleanup tasks remain in Todoist.

## After publication
Verify all page HTTP status codes, live canonicals, custom 404 status, robots/sitemap delivery, HTTPS redirects, booking and success redirect. Submit sitemap and inspect public pages in Search Console. Exclude success/404 from indexing.

## Page-speed source review
- Added preconnect hints for use.typekit.net and p.typekit.net on all six authored pages.
- Homepage references 889,756 bytes of images in total; 206,008 bytes are the eager logo and hero, with the remaining images lazy-loaded. Lazy-loading behavior depends on viewport proximity.
- Stylists page references 340,320 bytes of images, including the 52,280-byte eager logo; portraits are lazy-loaded.
- Services, Contact, Book and Success each reference only the 52,280-byte logo before external assets.
- Shared CSS, Adobe Fonts, and on Book the Vagaro loader/frame are additional costs, not included in these image totals.
- A local browser benchmark could not run because the Chromium download failed. No Lighthouse score, LCP, CLS, INP or network waterfall was measured. Preconnect benefit has not been benchmarked.
- Next: obtain a reachable site-revamp preview URL and run mobile/desktop PageSpeed Insights, especially Home, Stylists and Book. Do not use the current production homepage score to represent the unpublished revamp.
