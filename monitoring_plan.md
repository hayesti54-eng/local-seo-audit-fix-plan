# SEO Monitoring Plan
### Local Home Services | Post-Audit Ongoing Tracking

---

## Purpose

This plan defines the recurring monitoring cadence to sustain and build on the gains achieved through the initial audit and fix roadmap. It covers what to check, when to check it, which tools to use, and what to do if metrics move in the wrong direction.

Monitoring is broken into weekly checks (lightweight, 30-45 minutes) and monthly checks (deeper analysis, 2-3 hours).

---

## Weekly Checks (Every Monday Morning)

Weekly monitoring is designed to catch regressions and confirm that in-progress fixes are taking effect. These checks should take no longer than 45 minutes.

### 1. GSC Coverage Report - New Errors

- Open Google Search Console > Index > Pages
- Check for new error types that did not exist the prior week
- Pay particular attention to: "Server errors (5xx)", "Redirect error", and new "Crawled, currently not indexed" entries
- If new errors appear, log them in the fix backlog immediately and assign an owner

**Alert Threshold:** Any single new error type affecting more than 3 URLs triggers same-week investigation.

### 2. GSC Performance - Weekly Traffic Movement

- Open Performance > Search Results
- Set date range to Last 7 Days vs. Previous 7 Days
- Review total Clicks and Impressions delta
- Check for sudden drops on any top 10 pages (pages with most clicks)
- Look for any top service or location pages that lost more than 20% of clicks week over week

**Alert Threshold:** More than 20% drop in total clicks or any single key service page losing over 30% of weekly clicks triggers investigation.

### 3. Crawl Budget Check (Lightweight)

- If the site is being actively changed (new pages added, redirects updated), perform a targeted recrawl of changed URLs using Screaming Frog List Mode
- Verify that new pages return 200 status
- Verify no accidental noindex tags were introduced during publishing

### 4. GBP Check

- Log into Google Business Profile
- Check for new Q&A submissions that need a response
- Check for new reviews that need acknowledgement
- Verify no unexpected changes to business information (address, hours, category) - these can be edited by users or auto-updated by Google

### 5. Phone Number and NAP Spot Check

- Load the homepage and contact page on mobile
- Tap the phone number to confirm the tel: link is working correctly
- Confirm the address in the footer matches the GBP address exactly

---

## Monthly Checks (First Week of Each Month)

Monthly checks are more analytical and form the basis of the monthly performance report.

### 1. Full GSC Performance Report Export

- Export the full performance data for the last 28 days vs. the prior 28 days
- Pull data at both the page level and query level
- Review:
  - Total clicks and impressions trend
  - Average position movement for the top 30 pages
  - CTR changes on key service pages
  - New queries appearing in the top 50 that were not there last month

### 2. Coverage and Index Health Review

- Compare the number of indexed pages this month vs. last month
- Any pages moved from "Not indexed" to "Indexed" following content improvements should be logged as wins
- Check that the number of indexable pages in the XML sitemap matches or is close to the number of indexed pages in GSC

### 3. Full Screaming Frog Crawl

- Run a full site crawl on the first Monday of each month
- Compare the report to the prior month's crawl using the Screaming Frog crawl comparison feature
- Look for:
  - New 4xx or 5xx responses
  - New duplicate title tags introduced by CMS publishing activity
  - New pages with missing H1s
  - Any new pages excluded from indexation unexpectedly
  - Changes in internal link counts for key pages

### 4. Keyword Rank Tracking Review

- Log into rank tracking tool (e.g. Ahrefs, Semrush, or Local Falcon for local pack)
- Review position movement for the 20-30 tracked Service + Location keyword combinations
- Document: keywords that moved up 3+ positions, keywords that dropped 3+ positions
- Cross-reference rank movements with fix implementation dates to attribute causality

### 5. Local Pack Visibility Check

- Use Local Falcon or a manual near-me search to review GBP local pack presence
- Check the top 3 service keywords for each main suburb
- Note any changes to the local pack composition (new competitors appearing, current positions)
- If local pack visibility dropped, check: GBP health, NAP consistency, review volume/recency

### 6. Page Speed and Core Web Vitals

- Run the top 5 service pages through Google PageSpeed Insights (mobile and desktop)
- Log LCP, CLS, and FID/INP scores
- Flag any page where mobile LCP exceeds 4 seconds or CLS exceeds 0.1

### 7. Backlink Profile Snapshot

- Pull a monthly backlink report from Ahrefs or GSC > Links
- Note new referring domains acquired
- Check for any new toxic or spammy links that should be disavowed
- Track the total number of referring domains month over month

---

## KPIs to Review Monthly

These are the primary indicators of overall local SEO health.

| KPI | Measurement Method | Review Frequency | Target Direction |
|---|---|---|---|
| Total Organic Clicks | GSC Performance Report | Monthly (weekly trend) | Increasing |
| Total Organic Impressions | GSC Performance Report | Monthly | Increasing |
| Average CTR (Sitewide) | GSC Performance Report | Monthly | Increasing toward benchmark |
| Pages Indexed | GSC Coverage Report | Monthly | Stable or increasing |
| Coverage Errors | GSC Coverage Report | Weekly | Decreasing toward zero |
| Average Position (Top 30 Pages) | GSC Performance Report | Monthly | Decreasing (lower = better) |
| Local Pack Appearances | Local Falcon or manual | Monthly | Increasing |
| GBP Profile Views | Google Business Profile Insights | Monthly | Increasing |
| GBP Phone Calls (from GBP listing) | GBP Insights | Monthly | Increasing |
| New Reviews (GBP) | GBP Dashboard | Monthly | Increasing |
| Average Review Rating | GBP Dashboard | Monthly | Maintaining 4.0+ |
| Referring Domains | Ahrefs / GSC Links | Monthly | Stable or increasing |
| Mobile PageSpeed Score (Top Pages) | PageSpeed Insights | Monthly | Maintaining 70+ |

---

## GSC Metrics to Track in Detail

### Performance Report Metrics

| Metric | Page Level Focus | Query Level Focus |
|---|---|---|
| Clicks | Top 20 pages by clicks - track individually | Top 50 queries - note new entrants |
| Impressions | Pages with high impressions but low CTR | Queries where site appears but does not click |
| CTR | Flag pages below benchmark for their position | Flag queries where intent suggests a better page |
| Average Position | Track movement for each key service + location pair | Track branded vs non-branded position separately |

### Coverage Metrics

| Metric | What to Track |
|---|---|
| Total Indexed Pages | Month over month - note any drops of 5+ pages |
| Crawled Not Currently Indexed | Should decrease as thin content is improved |
| Discovered Not Indexed | Should decrease as internal linking is improved |
| Excluded - Noindex | Should remain stable (or decrease if any noindex issues are resolved) |
| Server Errors | Should be zero; any appearance triggers immediate fix |

---

## Crawl Health Metrics to Re-Check

After the initial audit, these metrics from Screaming Frog should be re-checked monthly and compared to the baseline crawl.

| Metric | Baseline (Demo) | Month 1 Target | Month 3 Target |
|---|---|---|---|
| Total URLs Crawled | 212 | 220 (new pages) | 230 |
| URLs Returning 200 | 174 (82%) | 195 (88%) | 215 (93%) |
| URLs Returning 3xx | 24 | 15 | 5 |
| URLs Returning 4xx | 8 | 3 | 0 |
| Pages with Missing Title Tags | 6 | 2 | 0 |
| Pages with Duplicate Title Tags | 11 | 4 | 0 |
| Pages with Missing H1 | 7 | 3 | 0 |
| Pages with Missing Meta Description | 14 | 6 | 0 |
| Orphaned Pages (0 inlinks) | 3 | 1 | 0 |
| Pages with No Schema | All (47) | 30 | 0 |
| Average Crawl Depth of Service Pages | 3.8 | 3.2 | 2.5 |

> All baseline figures are demo assumptions illustrating expected starting conditions for a home services site of similar size.

---

## Escalation Triggers

The following situations require same-day investigation rather than waiting for the next scheduled review:

- Total weekly organic clicks drop by 30% or more compared to the prior week
- A high-revenue service page falls out of the top 20 in GSC average position
- GSC Coverage report shows 10+ new server errors or 10+ new pages with a redirect error
- GBP listing is suspended or shows an "unverified" warning
- The XML sitemap becomes inaccessible (returns error in GSC Sitemaps report)
- A competitor appears in the local pack for a keyword where the business held position 1

---

*Monitoring Plan version 1.0 | Local SEO Audit Portfolio | 2026*
