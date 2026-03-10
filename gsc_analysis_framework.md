# Google Search Console Analysis Framework
### Local Home Services SEO | Performance and Coverage Workflow

---

## Purpose

This document outlines the structured workflow for extracting, interpreting, and acting on Google Search Console data during a local SEO audit. It is designed specifically for home services businesses with service area pages, a Google Business Profile, and a mix of branded and non-branded queries.

---

## 1. Performance Report Workflow

### Initial Setup and Data Range

Before extracting any data, configure the report correctly.

- Set the date range to **Last 16 Months** (maximum available) for trend identification
- Compare to the previous equivalent period to measure YoY movement
- Set Search Type to **Web** for core keyword analysis
- Run a separate pass with Search Type set to **Image** if the site has a gallery or project portfolio

### Metric Definitions

| Metric | What It Tells You |
|---|---|
| Clicks | Actual visits from organic search |
| Impressions | How often the site appeared in search results |
| CTR | Clicks divided by impressions - lower than expected = title/description problem |
| Average Position | Mean ranking across all queries the page appeared for |

### Baseline Report Steps

1. Open Performance > Search Results
2. Set date range to Last 3 Months
3. Export full query and page data as CSV (top right export button)
4. Open in Google Sheets for filtering and pivot analysis
5. Add a calculated column: `CTR Benchmark` based on average position (see CTR benchmarks below)

### CTR Benchmarks by Position (Local Search Reference)

| Average Position | Expected CTR Range |
|---|---|
| 1 | 25% - 35% |
| 2 | 12% - 18% |
| 3 | 8% - 12% |
| 4 - 5 | 5% - 8% |
| 6 - 10 | 2% - 5% |
| 11 - 20 | 0.5% - 2% |

Any URL where actual CTR falls more than 30% below benchmark for its average position is a priority for title tag and meta description review.

---

## 2. Coverage and Indexation Review

### Steps

1. Navigate to **Index > Pages** in GSC
2. Review the "Why pages aren't indexed" breakdown
3. Export each reason category separately for triage

### Coverage States to Investigate

| Status | Likely Cause | Action |
|---|---|---|
| Excluded - Noindex tag | robots meta or X-Robots header set to noindex | Confirm if intentional; remove if page should rank |
| Excluded - Crawled, not currently indexed | Thin content, low quality signals, or duplicate | Improve content depth and uniqueness |
| Excluded - Discovered, not indexed | Crawl budget issue or low internal link signal | Increase internal links; check crawl depth |
| Excluded - Alternate page with canonical tag | Duplicate content being correctly consolidated | Verify canonical points to the right URL |
| Excluded - Blocked by robots.txt | Robots.txt disallow rule | Check if block is intentional |
| Error - 404 | Broken URL was linked to or submitted in sitemap | Redirect or remove from sitemap |
| Error - Redirect error | Redirect chain or loop | Fix in .htaccess or redirect plugin |

> **Demo Finding:** During the audit, 6 suburb service area pages were sitting in "Crawled, currently not indexed" status. All 6 had word counts under 250 words and were near-identical templates with only the suburb name changed. The fix was to add 400+ words of unique local copy per page including references to nearby landmarks, local licensing context, and suburb-specific service notes.

### Sitemap Submission Check

- Navigate to **Sitemaps** in GSC
- Confirm the sitemap is submitted and returning no errors
- Check "Submitted" vs "Indexed" count - a large gap (over 20%) warrants investigation
- If XML sitemap includes 3xx or 4xx URLs, clean the sitemap and resubmit

### URL Inspection Tool Usage

Use the URL Inspection tool for specific pages that should be indexed but are not.

1. Paste the URL into the inspection bar
2. Click "Test Live URL" to see what Googlebot sees right now
3. Review: Last crawl date, indexing status, canonical confirmed by Google, mobile usability
4. If page is not indexed, click "Request Indexing" after fixing the underlying issue

---

## 3. Page and Query Review Process

### Page-Level Analysis

1. In Performance, click the **Pages** tab
2. Sort by Clicks descending - this is the current value list
3. Sort by Impressions descending - this shows reach regardless of ranking
4. Sort by Impressions descending but filter CTR under 3% - this surfaces high-reach, low-performance pages

For each page in the top 30 by impressions:
- Note average position
- Note CTR vs benchmark
- Click through to see which queries drive that page's impressions
- Identify the primary keyword intent and check if the page properly targets it

### Query-Level Analysis

1. In Performance, click the **Queries** tab
2. Sort by Impressions descending
3. Export the top 500 queries to CSV

In the spreadsheet, categorise each query into:

| Category | Example Queries |
|---|---|
| Branded | "apex plumbing", "apex plumber springfield" |
| Service + Location | "plumber in springfield", "emergency plumber near me" |
| Service Only | "drain cleaning", "hot water heater repair" |
| Informational | "how to fix a leaky tap", "why is my boiler making noise" |
| Competitor | "vs acme plumbing", "acme plumbing reviews" |

Focus optimisation effort on Service + Location queries. These drive the highest-intent local traffic.

### Query to Page Mapping

For each top Service + Location query:
1. Identify which page Google is ranking (from the page filter in the query row)
2. Check if that page is the intended landing page
3. If Google is ranking a blog post or contact page for a service + location query instead of the service page, this signals a content gap or cannibalisation issue

---

## 4. CTR Opportunity Analysis

CTR opportunity analysis identifies pages already ranking in positions 1-20 where a better title tag or meta description would generate more clicks without needing to rank higher.

### Process

1. Export the full Performance report (Queries + Pages with all metrics)
2. In your spreadsheet, filter to pages with Average Position between 1 and 15
3. Add a column: `Expected CTR` using the benchmark table above
4. Add a column: `CTR Gap` = `Expected CTR - Actual CTR`
5. Sort by CTR Gap descending
6. Pages with the largest positive gap are your highest-leverage CTR opportunities

### Diagnosing a Low CTR

Before rewriting a title tag, check the following:

- **Is the title tag cut off in SERPs?** Characters over 60 may be truncated, hiding the location modifier or CTA
- **Does the snippet include the city/area?** Google may rewrite the title in SERPs if it deems the page more relevant to a different query
- **Is the meta description compelling?** A weak meta description increases bounce intent before the click even happens
- **Are competitors using structured snippets, reviews, or sitelinks that push your result down visually?**

> **Demo Finding:** The `/services/hot-water-repair/` page had an average position of 4.2 across 12 local search queries but a CTR of only 2.1%, well below the expected 7-8% for that position. The title tag read "Hot Water Repair | Apex Plumbing" with no location. Updating it to "Hot Water System Repair in Springfield | 24/7 | Apex Plumbing" and rewriting the meta description to include "same-day service" resulted in a projected click volume increase of 60-80 additional clicks per month.

---

## 5. Page Prioritisation Methodology

Not all pages can be improved simultaneously. This framework scores each URL to determine order of work.

### Prioritisation Scoring Matrix

Rate each page on the following criteria on a scale of 1 to 3:

| Criteria | 1 (Low) | 2 (Medium) | 3 (High) |
|---|---|---|---|
| Search Impressions | Under 100/month | 100-500/month | Over 500/month |
| Business Revenue Potential | Low-value service | Mid-tier service | High-ticket service |
| Current Position | Position 20+ | Position 11-19 | Position 4-10 |
| Ease of Fix | Requires dev + content | Content only | Title/meta only |
| Conversion Page? | Info/blog page | Service category | Direct service + location |

**Priority Score** = Sum of all five scores. Maximum score is 15.

Pages scoring 12-15: Fix in Phase 1
Pages scoring 8-11: Fix in Phase 2
Pages scoring 7 or below: Fix in Phase 3 or deprioritise

### Applying the Matrix

1. Pull the top 50 pages by impressions from GSC
2. Score each against the five criteria
3. Sort by Priority Score descending
4. This becomes the content and technical fix queue

> **Demo Finding:** Using this matrix, the `/service-area/riverside/plumbing/` page scored 14/15: high impressions, high revenue potential (full plumbing service), current position at 7, fix required only a title tag and meta update, and it was a direct local service page. It was elevated to Phase 1 alongside the robots.txt fix.

---

## GSC Data Quality Notes

- GSC data has a 2-4 day reporting delay; do not use the last 3 days for analysis
- Position data is an average across all queries for that URL; a page may rank 2 for one query and 18 for another, averaging to 10
- Impressions are logged even if the user never scrolls to the result
- GSC truncates query data: queries with very few impressions are grouped into "other" and will not appear in the export

---

*Framework version 1.0 | Local SEO Audit Portfolio | 2026*
