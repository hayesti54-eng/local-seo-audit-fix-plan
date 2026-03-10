# Screaming Frog Audit Framework
### Local Home Services SEO | Technical and On-Page Crawl Guide

---

## Purpose

This document outlines the complete Screaming Frog crawl setup and review process used in the local SEO audit. It is structured so that any SEO analyst can replicate the workflow on a similar home services site.

---

## 1. Crawl Scope and Configuration

### Pre-Crawl Setup

Before launching the crawl, complete the following configuration steps in Screaming Frog.

**Mode:** Spider (not List mode unless re-crawling specific URLs)

**Crawl Scope Settings:**
- Set the crawl to start from the root domain (e.g. `https://www.example-plumbing.com`)
- Include subdomains only if the site actively uses them (e.g. `blog.example.com`)
- Exclude `/wp-admin/`, `/cart/`, `/checkout/`, and parameter-heavy URLs if applicable

**Configuration > Spider Settings:**
- Check "Crawl Linked XML Sitemaps" to catch any pages outside the main crawl path
- Enable "Store Rendered HTML" if the site uses JavaScript rendering (React, Vue, etc.)
- Set "Max URL" to at least 10,000 for a site with many service area pages

**User Agent:**
- Set to Googlebot (Desktop) for the primary crawl
- Run a second crawl with Googlebot (Mobile) to catch mobile-specific issues

**Authentication:**
- If the site has password-protected staging pages in the same subdirectory, set HTTP auth credentials in Configuration > HTTP Header

**Custom Extraction (Optional but Recommended):**
- Set up XPath or CSS extraction to pull schema markup presence, GBP embed presence, and review widget presence
- Custom extraction for `<meta name="robots">` content to catch noindex tags at element level

---

## 2. Key Tabs and Reports to Review

Work through these tabs in order after the crawl is complete.

### Internal Tab

This is the primary working view for technical and on-page issues.

| Column to Review | What to Look For |
|---|---|
| Status Code | Filter for 3xx, 4xx, 5xx |
| Title 1 | Blanks, duplicates, over 60 characters, keyword gaps |
| Meta Description 1 | Blanks, duplicates, over 160 characters |
| H1-1 | Blanks, duplicates, H1 used more than once per page |
| Word Count | Pages under 300 words (thin content candidates) |
| Indexability | "Non-Indexable" filter reveals noindex, canonical mismatches |
| Canonical | Compare against Address column to spot self-referential vs. redirect canonicals |
| Crawl Depth | Pages at depth 4+ may need internal linking attention |

### Response Codes Tab

Filter by status to work through each code type:

- **301/302:** Map each redirect to its destination. Flag chains (A > B > C) and loops.
- **404:** Identify broken pages that were once linked to. Check if they have inbound links worth recovering.
- **5xx:** Server errors often point to hosting or plugin conflicts on WordPress sites.

### Page Titles Tab

- Filter "Duplicate" to find templated title tag problems
- Filter "Over 60 Characters" and "Under 30 Characters"
- Export and paste into a spreadsheet for rewriting with local keyword templates

### Meta Description Tab

- Filter "Missing" - priority for any page receiving GSC impressions
- Filter "Duplicate" - common on location page templates

### H1 Tab

- Filter "Missing" - signals a structural content problem or theme issue
- Filter "Multiple" - some local sites accidentally use H1 twice due to widget/plugin conflicts
- Filter "Over 70 Characters" - H1s should be specific and readable

### Images Tab

- Filter "Missing Alt Text" - important for service pages with before/after job photos
- Filter images over 100KB - page speed issue on image-heavy home services sites

### Links Tab (Internal)

- Review "Inlinks" column for each URL - pages with 0 or 1 inlink are effectively orphaned
- Check anchor text distribution for over-optimised exact match anchors

### Sitemaps Tab

- Compare URLs in the XML sitemap against what was actually crawled
- URLs in sitemap but returning 404 or noindex are common issues on local sites

---

## 3. Technical Checks

### Crawlability

- [ ] Verify robots.txt is accessible at `/robots.txt`
- [ ] Check that core service pages and location pages are NOT disallowed
- [ ] Confirm XML sitemap is listed in robots.txt and is reachable
- [ ] Verify sitemap contains all indexable URLs (no 3xx/4xx URLs included)
- [ ] Check that no important pages are set to `noindex` via meta robots or X-Robots-Tag header

> **Demo Finding:** During the audit, two suburb-level service area pages (`/service-area/springfield/` and `/service-area/riverside/`) were found blocked by a wildcard disallow rule added during a previous site migration. Both pages had GSC impressions data, confirming they were previously indexed.

### HTTPS and Canonicalisation

- [ ] Confirm all HTTP URLs redirect to HTTPS equivalents
- [ ] Check trailing slash consistency (pick one pattern and enforce it sitewide)
- [ ] Verify canonical tags on all pages point to the correct, live URL
- [ ] Confirm no redirect chains longer than two hops

### Page Speed Signals (Screaming Frog + PageSpeed Integration)

- Enable Configuration > API Access > PageSpeed Insights (requires a Google API key)
- Review LCP, CLS, and FID scores per URL
- Flag any service page scoring below 50 on Mobile Performance

### Structured Data

- Use Configuration > Custom Extraction or the Structured Data report (if using SF v19+)
- Check for presence of LocalBusiness, Service, BreadcrumbList, and FAQPage schema
- Flag pages with no schema markup

---

## 4. On-Page Checks

Focus on service pages, location pages, and the homepage. These drive the most local ranking value.

### Title Tag Review

- Target pattern for service pages: `[Service] in [City] | [Brand Name]`
- Example: `Emergency Plumber in Springfield | Apex Plumbing`
- Flag any title tags that omit the city/area modifier
- Flag duplicate titles across suburb variants of the same service

### H1 Review

- H1 should match or closely mirror the title tag intent
- Should include the primary service keyword and location
- Should appear once per page, above the fold
- Should not duplicate the site name or navigation label

### Meta Description Review

- Target 140-155 characters
- Should include a value proposition and a soft call to action (e.g. "Call today for a free quote")
- Should reference the service and location
- Not a direct ranking factor, but critical for CTR

### Content Depth Check

- Export word count per URL from the Internal tab
- Flag pages under 300 words as thin content
- Flag pages where word count is identical across suburb variants (copy-paste templates)
- Ideal word count for local service pages: 500-800 words with unique local references

### Local Signals on Page

- [ ] NAP (Name, Address, Phone) visible in footer and on contact page
- [ ] Phone number is clickable (tel: link) on mobile
- [ ] Service area mentioned in at least the H1 or first paragraph
- [ ] Embedded Google Map present on location and contact pages
- [ ] Customer review markup or review widget visible

---

## 5. Internal Linking Checks

Internal linking is one of the most underutilised levers in local SEO audits.

### Link Distribution

- From the Links tab, sort by "Inlinks" ascending
- Any service or location page with fewer than 3 internal links is underlinked
- Orphaned pages (0 inlinks from crawled pages) may not be discovered by Google at all

### Anchor Text Audit

- Export anchors from the Bulk Export > Links > All Inlinks report
- Review for generic anchors like "click here" or "read more" that miss keyword opportunity
- Flag over-optimised patterns if the same exact-match anchor repeats excessively

### Navigation and Hub Pages

- [ ] Does the homepage link to all main service category pages?
- [ ] Do service category pages link to all suburb variants?
- [ ] Do suburb pages cross-link to related services (e.g. plumbing page links to drain cleaning page in same suburb)?
- [ ] Is breadcrumb navigation present sitewide?

> **Demo Finding:** The homepage linked directly to only 4 of 14 service pages. The remaining 10 were only accessible from a mega-menu dropdown that search engine bots may not follow consistently.

### Link Depth

- From the Internal tab, filter by "Crawl Depth" greater than 4
- Pages at depth 5+ often rank poorly due to PageRank dilution
- Local service area pages should be reachable within 3 clicks from the homepage

---

## 6. Export Recommendations

The following exports should be saved and shared with the wider team or client.

| Export Name | Screaming Frog Path | Use |
|---|---|---|
| All URLs (Internal) | Bulk Export > Response Codes > All | Base URL inventory |
| Redirect Chains | Reports > Redirect Chains | Developer fix list |
| Duplicate Title Tags | Bulk Export > Page Titles > Duplicate | Content rewrite list |
| Duplicate Meta Descriptions | Bulk Export > Meta Descriptions > Duplicate | Content rewrite list |
| Missing H1s | Bulk Export > H1 > Missing | Developer / content fix |
| Missing Alt Text | Bulk Export > Images > Missing Alt Text | Developer fix list |
| Orphaned Pages | Links tab filtered by Inlinks = 0 + manual export | Internal linking plan |
| Sitemap vs Crawl Discrepancies | Reports > Sitemap > In Sitemap not Crawled | Sitemap cleanup |
| XML Sitemap URLs | Sitemaps tab | Verify all key pages are included |

All exports should be saved in `.csv` format and dated. Keep raw exports in a `/crawl-exports/` subfolder separate from the working analysis documents.

---

*Framework version 1.0 | Local SEO Audit Portfolio | 2026*
