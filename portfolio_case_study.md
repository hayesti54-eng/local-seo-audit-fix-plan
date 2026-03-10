# Portfolio Case Study: Local SEO Audit and Fix Plan
### HHH Roofing & Construction | Houston, TX | Technical + On-Page + Local SEO

---

## Business Context

**Business:** HHH Roofing & Construction  
**Industry:** Roofing and construction  
**Location:** Houston, Texas  
**Primary Focus:** Residential and commercial roofing  
**Site Type:** Local home services website with service pages, location pages, and commercial roofing pages  
**Audit Scope:** Houston-focused crawl and page review using Screaming Frog plus manual on-page analysis

This case study documents a real local SEO audit completed on HHH Roofing & Construction's Houston web presence. The project focused on identifying technical and on-page issues affecting crawl efficiency, local page targeting, metadata quality, internal linking, and service-intent alignment.

---

## The Challenge

HHH Roofing has a strong visual brand, clear service segmentation, and visible conversion intent across its residential and commercial roofing pages. The site already includes local trust elements and Houston-specific messaging, which creates a strong foundation for local SEO.

However, the crawl and page review revealed several issues that may reduce visibility and efficiency in organic search:

- legacy URLs still present in the crawl
- redirects across service and location variants
- a broken commercial-intent page
- overlength title tags and meta descriptions
- missing H1 tags on selected pages
- canonical handling that needs validation
- possible overlap between broad Houston pages and narrower service-intent pages

The central question was not whether the site needed a full rebuild, but where focused technical and on-page improvements could produce the strongest local SEO gains.

---

## Audit Process

### Phase 1: Crawl Setup and Scope Definition

The audit began with a Screaming Frog crawl of the Houston section and linked pages within the HHH Roofing site.

The crawl was used to review:

- internal URLs
- response codes
- title tags
- meta descriptions
- H1 structure
- canonical implementation
- directives
- internal linking patterns

A manual page review followed to assess:

- local keyword alignment
- trust signals
- CTA placement
- residential vs commercial service segmentation
- overlap between broad location pages and narrower service pages

---

## Key Crawl Findings

The crawl surfaced a focused but meaningful set of issues.

### Response Codes
- 36 internal URLs identified in the crawl set
- 33 successful 2xx URLs
- 12 redirects
- 1 client error 4xx

This is a relatively high redirect count for a small crawl, suggesting legacy URL patterns and internal-link cleanup opportunities.

### Broken URL
One broken page was identified:

- `/houston-tpo-roofer` returned **404 Not Found**

This appears to be a legacy commercial/local-intent URL and should either be redirected to the most relevant live commercial TPO page or restored if it previously had ranking value or backlinks.

### Redirect Behavior
A redirected Houston TPO URL was also identified:

- `/tpo-roof/houston/` returned **301 Moved Permanently**

This raises an intent-mapping concern. If a commercial TPO Houston query path is redirected to a broader Houston page instead of a service-specific destination, the redirect may preserve URL equity but weaken service relevance.

---

## Metadata Findings

### Title Tags
- 0 missing
- 0 duplicate
- 10 over 60 characters
- 2 below 30 characters
- 10 over recommended pixel width

This indicates that title-tag coverage is strong, but optimisation is still needed. The issue is not missing titles. It is overlength, under-optimised, or inconsistent presentation in search results.

### Meta Descriptions
- 0 missing
- 0 duplicate
- 11 over 155 characters
- 9 over recommended pixel width

This suggests the site has solid metadata coverage but weak snippet discipline. Descriptions are often too long and may truncate in SERPs, reducing CTR control.

---

## Heading and Structure Findings

### H1 Review
- 4 pages missing H1 tags
- 0 duplicate H1s
- 3 pages with non-sequential heading structure

Missing H1 tags weaken page-topic clarity and can make it harder for Google to understand the intended keyword focus of a page.

### Canonicals
- 23 pages contained canonicals
- 22 were self-referencing
- 1 page was canonicalised
- 1 page was marked non-indexable canonical

At least one page requires validation to ensure the correct URL is being treated as the ranking version.

### Directives
- 23 pages indexed
- 0 noindex pages
- 23 follow directives

This is a positive finding. The site does not appear to suffer from widespread noindex misuse. The larger issues are around redirects, broken URLs, metadata quality, and page targeting.

---

## Internal Linking Findings

The crawl showed shallow page depth overall, which is positive.

However, there were still internal-link quality concerns:

- many pages appeared to rely on weak or non-descriptive internal link implementation
- internal outlinks with no anchor text appeared across the crawl
- money pages may not be receiving enough contextual internal-link support

This is especially important on a site where service and location intent need to be clearly reinforced.

---

## Manual Page Review Findings

### Houston Residential Page
The Houston residential page demonstrated several strong local SEO elements:

- clear H1: **Residential Roofing in Houston, TX**
- strong local modifiers including **The Heights, River Oaks, Memorial, Bellaire, and Montrose**
- clear CTAs including call and schedule actions
- trust language including **Licensed & Insured**
- visible proof-oriented section: **Trusted By Houston Homeowners**

This page already has a solid conversion and local relevance foundation.

### Commercial TPO Page
The TPO page also performed well from a service-intent perspective:

- clear commercial service positioning
- relevant commercial roofing copy
- trust badges and supplier logos
- visible CTA and phone number
- strong topical specificity compared with the broader Houston page

This page should be treated as a priority money page and supported accordingly.

---

## What Was Working Well

The audit did not reveal a weak site overall. In fact, several areas were already strong:

- clear residential vs commercial service segmentation
- strong Houston-local language on key pages
- visible trust elements and strong CTA placement
- shallow crawl depth across core pages
- broad title and description coverage across the crawl
- no widespread duplicate-title problem
- no large-scale noindex issue across key pages

This matters because the project is not about rebuilding the site from scratch. It is about cleaning up friction points that can suppress visibility.

---

## Key Findings Summary

| Finding | Severity | Why It Matters |
|---|---|---|
| `/houston-tpo-roofer` returns 404 | High | Broken commercial/local-intent URL may waste link equity and create dead-end crawl paths |
| 12 redirects in a small crawl set | High | Suggests legacy URL dependency and internal-link cleanup opportunities |
| `/tpo-roof/houston/` returns 301 | High | Redirect may not preserve commercial service intent if mapped too broadly |
| 10 title tags exceed display length guidance | Medium-High | Increased truncation risk and weaker CTR control |
| 11 meta descriptions exceed best-practice length | Medium | Reduced snippet clarity in search results |
| 4 pages missing H1 tags | High | Weakens page-topic clarity and on-page targeting |
| 1 page canonicalised / non-indexable | High | Needs validation to ensure the right page can rank |
| Internal links appear weak in contextual anchor support | Medium | Limits reinforcement of priority service pages |
| Broad Houston page may overlap with narrower service-intent pages | Medium-High | May dilute local relevance if page roles are not clearly separated |

---

## Prioritisation Logic

Issues were prioritised using a simple framework:

1. **SEO Impact**  
How strongly does the issue affect crawlability, indexation, or relevance?

2. **Business Impact**  
Does the issue affect a revenue-driving page such as a residential Houston page or commercial roofing service page?

3. **Effort Level**  
Can the issue be fixed quickly through metadata, redirects, or internal-link updates, or does it require deeper structural work?

The highest-priority issues were the ones that combined strong SEO impact with relatively low or medium implementation effort.

---

## Recommended Fix Roadmap

### Phase 1: Technical Cleanup
- redirect `/houston-tpo-roofer` to the most relevant live commercial TPO page
- audit all 3xx URLs and update internal links to point directly to final 200 URLs
- validate where `/tpo-roof/houston/` resolves and confirm the destination matches commercial service intent
- review the canonicalised non-indexable page and confirm the correct ranking URL

### Phase 2: On-Page Optimisation
- rewrite overlength title tags across priority service and location pages
- improve short title tags where needed
- shorten meta descriptions for clearer SERP presentation
- add missing H1 tags and correct heading hierarchy issues

### Phase 3: Internal Linking and Intent Alignment
- strengthen internal links from broad hub pages to specific commercial and residential money pages
- add more descriptive contextual anchor text to service pages
- clarify the role of the broad Houston page versus narrower service-intent pages
- reduce overlap between general Houston targeting and commercial roofing intent

### Phase 4: Monitoring
- re-crawl the Houston section after fixes
- confirm removal of the 404 and cleanup of redirect dependency
- compare title, description, and H1 coverage after updates
- monitor visibility and engagement changes through future GSC reporting

---

## Expected SEO Impact

Because this project is based on a live site review rather than full GSC access, projected impact should be framed conservatively.

### Likely Outcomes From Fixes
- improved crawl efficiency through reduced redirect dependency
- better preservation of service intent on commercial roofing URLs
- improved click-through rate from cleaner titles and meta descriptions
- stronger topical clarity on pages currently missing H1s
- better reinforcement of priority money pages through internal links
- clearer separation between broad Houston intent and narrower residential/commercial service intent

---

## What This Project Demonstrates

This project demonstrates the ability to:

- run a live Screaming Frog crawl on a real home services website
- identify technical SEO issues that matter in local search, not just generic crawl warnings
- interpret metadata, heading, canonical, and redirect issues in business terms
- assess local page quality through both crawl data and manual review
- translate findings into a prioritised, execution-ready roadmap

---

## Learning Outcomes

### What the Audit Confirmed
1. A site can have a strong local SEO foundation while still losing performance through technical friction and unclear intent mapping.
2. Not all redirect issues are equal. A redirect that preserves traffic but weakens topical alignment can still hurt SEO performance.
3. Metadata coverage alone is not enough. Length, clarity, and local targeting still matter.
4. Local service pages need both technical cleanliness and strong trust/conversion structure to perform well.
5. Manual review is essential in local SEO because screenshots, CTAs, trust badges, and page positioning often reveal issues that crawl data alone cannot.

### What I Would Do Next
- add full GSC validation to compare page-level clicks, impressions, CTR, and position
- inspect backlink value on broken or redirected legacy URLs
- review inlinks to commercial roofing pages more deeply
- expand the audit into structured data, image optimisation, and GBP alignment

---

## Conclusion

HHH Roofing & Construction already has many of the ingredients of a strong local home services site: local relevance, trust signals, clear service segmentation, and visible conversion paths.

The biggest opportunity is focused refinement:

- clean up legacy URLs
- reduce redirect dependency
- improve metadata presentation
- fix missing headings
- validate canonical handling
- strengthen internal-link support to key service pages
- better separate broad Houston intent from narrower commercial roofing intent

That combination would make the site more technically efficient, more contextually clear, and better positioned to capture high-intent local traffic.

---

*Case Study version 2.0 | Real Business Audit | HHH Roofing & Construction | 2026*
