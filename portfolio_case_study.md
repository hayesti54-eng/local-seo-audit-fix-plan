# Portfolio Case Study: Local SEO Audit and Fix Plan
### Home Services Business | Technical + On-Page + Local SEO

> **Note:** All business details, URLs, and metrics in this case study are demo assumptions created to demonstrate real-world audit methodology. They do not represent a named client.

---

## Business Context

**Business Type:** Residential home services (plumbing, HVAC, electrical)
**Location:** Metro area + 14 suburban service areas
**Site Size:** ~210 pages (service pages, location pages, blog posts, utility pages)
**CMS:** WordPress with Yoast SEO plugin
**Audit Trigger:** Organic leads declining over 4 months despite no known site changes; new competitor appearing in local pack

---

## The Challenge

The business had been operating for 11 years and historically relied on word-of-mouth and Google Business Profile rankings. Over the preceding 12 months, a newer local competitor had invested in their website and was outranking the client for high-intent searches like "plumber in Springfield" and "emergency plumber near me."

The client's site had grown organically over several years with no deliberate SEO strategy. Service area pages had been created by a web designer who used a copy-paste template, and a robots.txt change during a WordPress theme migration had inadvertently blocked key pages.

The core question was: what is preventing the site from ranking for the local service keywords it should be winning, and what is the most efficient sequence of fixes?

---

## Audit Process

### Phase 1: Discovery and Tool Setup (Day 1-2)

The first step was establishing what data was available.

- Verified GSC property ownership and confirmed the site had 13 months of performance data
- Checked GSC Coverage immediately - the coverage report alone confirmed that 6 pages were in "Crawled, currently not indexed" status, which was an early red flag
- Submitted the XML sitemap URL to confirm it was live and accepted
- Set up Screaming Frog with Googlebot (Desktop) user agent and configured API access to Google PageSpeed Insights

**Key early observation:** The sitemap was submitted to GSC but 9 of the URLs inside it were returning 301 redirects to slightly different URL patterns. GSC was counting these as valid submitted URLs but they were not the canonical versions. This created a measurement gap between what was submitted and what was actually indexed.

### Phase 2: Screaming Frog Full Crawl (Day 2-3)

The crawl completed across 212 URLs in approximately 18 minutes.

The first review pass focused on the response codes tab:
- 24 redirects identified (11.3% of all crawled URLs)
- 8 pages returning 404 - all were old blog posts that had been deleted but not redirected
- 0 server errors (positive sign - no hosting instability)

The second pass focused on on-page elements:
- Sorted the Internal tab by Title 1 and immediately noticed multiple pages sharing identical title tags
- Filtered Word Count to show pages under 300 words - 8 pages appeared including 6 suburb service area pages
- Checked the H1 column - 7 pages had no H1 at all; 2 had multiple H1 tags

The third pass focused on internal linking:
- Ran Bulk Export > Links > All Inlinks
- Identified 3 pages with zero inlinks from any other crawled page
- Mapped crawl depth: the suburb service pages were sitting at depth 4-5, meaning Googlebot had to follow 4-5 links from the homepage to reach them

### Phase 3: GSC Performance Analysis (Day 3-4)

Exported the full performance report for the last 3 months (queries and pages combined).

**Top finding - CTR gaps:** Several service pages were ranking in positions 3-7 but had CTR values well below benchmark. This signalled a title and meta description problem rather than a ranking problem.

- `/services/hot-water-repair/` ranked at position 4.2 average for 12 related queries but had 2.1% CTR. Expected CTR at position 4 is roughly 7-8%. The title tag read "Hot Water Repair | Apex Plumbing" - no location, no urgency, no differentiation from every other result on the page.
- `/service-area/riverside/` had 890 impressions in 3 months but only 6 clicks. Average position was 11.4. The page was not indexed by Google at all during most of the period - the impressions came from the domain appearing for broader suburb-based searches rather than the specific page ranking.

**Top finding - unindexed suburb pages:** The 6 suburb pages in "Crawled, currently not indexed" status had a combined 1,400 impressions per month in GSC, meaning the domain was appearing in SERPs for those suburb queries but users were being sent to the wrong page (usually the homepage). If those suburb pages were indexed and properly optimised, click volume should improve significantly.

**Top finding - robots.txt block:** Cross-referencing the Screaming Frog crawl against GSC URL Inspection confirmed that `/service-area/springfield/` and `/service-area/riverside/` were blocked by robots.txt. Both had historical GSC data before the block was applied. This was a regression introduced during the previous theme update.

### Phase 4: Local SEO Signals Review (Day 4)

A separate manual check was performed outside of Screaming Frog and GSC:

- Audited GBP listing: primary category was set to "Contractor" rather than "Plumber." This was likely costing the business placement in category-filtered local pack results.
- Checked NAP across 12 citation sources: 3 sources listed the abbreviated business name and 1 used an old phone number from before the business moved premises.
- Confirmed no structured data was implemented across any page using Google's Rich Results Test and the GSC Enhancements tab (empty - no schema detected at all).

---

## Key Findings Summary

| Finding | Severity | Estimated Impact |
|---|---|---|
| Robots.txt blocking 2 suburb service pages | Critical | High - direct indexation loss |
| 9 redirect chains across internal links and sitemap | High | Link equity dilution, crawl inefficiency |
| 3 orphaned service pages | High | Pages invisible to crawlers without sitemap |
| 6 suburb pages thin/duplicate - not indexed | High | Missing suburb-level organic traffic |
| 11 duplicate title tags on service pages | High | Cannibalisation, weak click signal |
| 7 pages missing H1 | Medium | On-page relevance signal missing |
| No schema markup sitewide | High | Missing rich result eligibility, weaker local signals |
| GBP category mismatch | High | Local pack category filter exclusion |
| NAP inconsistency across 3 citations | Medium | Local authority dilution |
| CTR gap on hot-water repair page | Medium | Lost clicks from existing ranking |
| Homepage links to only 4 of 14 service pages | High | Internal PageRank concentration, orphaning |

---

## Prioritisation Logic

Issues were scored using a three-factor priority matrix:

1. **SEO Impact:** How significantly does this issue affect crawlability, indexation, or ranking potential? Scored 1-3.
2. **Business Impact:** Does fixing this issue affect a high-revenue service or a low-traffic edge page? Scored 1-3.
3. **Effort Level:** How much developer or content time does the fix require? Inverse scored (Low effort = 3, High effort = 1).

Priority Score = SEO Impact + Business Impact + Effort Score. Maximum 9.

Issues scoring 8-9 were designated P1 (fix within 2 weeks). Issues scoring 5-7 were P2 (fix within 6 weeks). Issues scoring 4 or below were P3 (fix in Phase 3 or deprioritise).

The robots.txt block scored 9/9: high SEO impact, high business impact, and required only a single line edit in the robots.txt file. It was the first fix actioned.

The full schema implementation scored 7/9: high SEO and business impact but moderate developer effort to implement across all pages. Moved to Phase 2.

The image alt text cleanup scored 4/9: low SEO impact for ranking, low business impact, and moderate effort across 43 images. Moved to Phase 3.

---

## Fix Roadmap

### Phase 1 - Immediate Fixes (Weeks 1-2)

- Remove robots.txt disallow rule blocking `/service-area/*`
- Update all 9 redirect chains to point directly to canonical destination URLs
- Update XML sitemap to remove 4xx URLs and add 3 previously orphaned service pages
- Fix GBP primary category from "Contractor" to "Plumber"
- Add location modifiers to title tags on 8 suburb service pages (content-only change, no developer required)

**Expected outcome:** Improved crawlability and indexation for suburb pages; improved local pack category eligibility; small CTR lift from title tag changes.

### Phase 2 - Core On-Page Improvements (Weeks 3-6)

- Rewrite title tags and meta descriptions for all 14 service pages using the local keyword template
- Add H1 tags to the 7 pages missing them
- Implement LocalBusiness and Service JSON-LD schema on all service and location pages
- Add unique introductory copy (400+ words) to the 6 thin suburb service pages
- Fix NAP inconsistencies across 3 citation sources

**Expected outcome:** Improved relevance signals for target keywords; eligibility for rich results; suburb pages moving from "not indexed" to "indexed" in GSC within 4-8 weeks.

### Phase 3 - Structural and Content (Weeks 7-12)

- Restructure internal linking: homepage links to all 14 service pages; hub pages link to suburb variants
- Implement breadcrumb navigation sitewide with BreadcrumbList schema
- Add FAQ sections and FAQPage schema to top 8 service pages
- Compress 18 oversized images to WebP; add descriptive alt text to all 43 flagged images
- Add contextual cross-links between suburb pages and related services

**Expected outcome:** Improved crawl efficiency and PageRank distribution across service pages; improved organic visibility for long-tail FAQ and informational queries.

---

## Expected SEO Impact

All projections below are based on conservative estimates and are demo assumptions. Real results depend on competition, search volume, and implementation quality.

| Metric | Pre-Audit Baseline | Projected 3-Month Outcome | Projected 6-Month Outcome |
|---|---|---|---|
| Indexed Service/Location Pages | 41 of 47 | 47 of 47 | 47 of 47 |
| Monthly Organic Clicks | ~820 | ~1,100 - 1,300 | ~1,400 - 1,700 |
| Pages with Title Tag + Location Modifier | 3 of 14 service pages | 14 of 14 | 14 of 14 |
| Local Pack Appearances (Top 3 Keywords) | 1 of 3 | 2 of 3 | 3 of 3 |
| Pages with Schema Markup | 0 | 12 | 47 |
| Hot Water Repair Page CTR | 2.1% | 5-6% | 6-8% |

---

## Learning Outcomes

### What the Audit Confirmed

1. **Robots.txt is often overlooked during migrations** and can quietly block high-value pages for months before being noticed. A robots.txt check should be one of the first steps in any site audit.

2. **GSC Coverage data reveals a different story to ranking data.** The site was "appearing" in GSC Performance for suburb queries, but those suburbs were not indexed. Performance data showing impressions can mask the fact that the actual target page is not ranking at all.

3. **Template-built local sites carry significant duplicate content risk.** The suburb pages on this site were built fast and cheaply, but the near-identical content was the primary reason 6 pages were excluded from the index. Content investment per page is not optional for competitive local markets.

4. **Internal linking is the easiest lever with the highest leverage for local SEO.** Three service pages were invisible to crawlers simply because no other page linked to them. No new content, no new links, no development work required - just an update to the navigation and hub pages.

5. **GBP category is a local pack filter.** Sitting in the wrong GBP category removes the business from appearing when users filter results by service type. This single fix required no technical work and had potential immediate local pack impact.

### What I Would Do Differently

- In future audits, I would run the GBP and NAP check in parallel with the crawl rather than after it. Local signals and technical signals interact, and understanding both early helps prioritise more accurately.
- I would also set up rank tracking before beginning the audit to have a pre-fix baseline to measure against. In this audit, the pre-audit rank data was reconstructed from GSC historical data, which is an approximation.

---

*Case Study version 1.0 | Local SEO Audit Portfolio | 2026*
