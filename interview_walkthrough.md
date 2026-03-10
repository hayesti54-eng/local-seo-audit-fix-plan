# Interview Walkthrough Guide
### How to Present This Local SEO Audit in an Interview or Portfolio Review

---

## Purpose

This guide helps you walk through this project confidently in a job interview, freelance pitch, or portfolio review. It covers how to narrate the audit process, explain tool decisions, and demonstrate strategic thinking rather than just listing actions taken.

The goal is to show that you can think like a consultant, not just execute a checklist.

---

## How to Frame the Project at the Start

Before jumping into the details, set the scene with a 30-45 second framing statement. This tells the interviewer or reviewer what problem you were solving and why it mattered.

**Example framing:**

> "This project was a technical and on-page local SEO audit for a home services business in a competitive metro area. The site had been around for over a decade but organic leads were declining and a newer competitor was outranking them for their core service keywords. My job was to diagnose why, prioritise the fixes, and hand the team a roadmap they could actually execute. I used Screaming Frog for the technical and on-page crawl and Google Search Console for the performance and indexation analysis."

This framing accomplishes four things:
1. It establishes context (local, home services, competitive)
2. It signals the business problem (not just an abstract SEO task)
3. It shows you made tool decisions deliberately
4. It positions you as someone who delivers outcomes, not just audits

---

## Walking Through the Audit Process

When asked "walk me through what you did," use this narrative structure.

### Step 1: Start with the Data You Had

> "Before I touched Screaming Frog, I went into Google Search Console to understand the current state. The Coverage report immediately showed 6 suburb pages in 'Crawled, currently not indexed' - that told me there was likely a content quality or duplicate content issue on those pages before I even ran the crawl. It also showed zero pages in 'Server Error', which ruled out a hosting problem."

**Why this matters:** It shows you go to GSC first to form a hypothesis, rather than just firing up a crawl and reacting to whatever it returns.

### Step 2: Set Up the Crawl Deliberately

> "When I set up Screaming Frog, I made a few deliberate configuration choices. I set the user agent to Googlebot Desktop and enabled 'Crawl Linked XML Sitemaps' so I wouldn't miss any pages that weren't linked internally. I also enabled the PageSpeed API integration to get Core Web Vitals data per URL in one pass rather than checking each page manually."

**Why this matters:** Most people just open Screaming Frog and hit crawl. Talking through configuration choices shows you understand what the tool is doing and why.

### Step 3: Show You Worked Through the Data Systematically

> "After the crawl I worked through the key tabs in a structured order. I started with Response Codes - that's where I found 24 redirects and 8 broken pages. Then I moved to Page Titles, filtered for duplicates, and found 11 service pages sharing the same basic title pattern with no location modifier. Then the H1 tab - 7 pages had no H1 at all."

> "The finding that connected everything was in the Links tab. Three service pages had zero inlinks from any other crawled page. They existed in the sitemap but were invisible to Googlebot unless it was following the sitemap specifically. That explained why they had impressions in GSC but very little click traffic - the domain was appearing but those pages were not ranking."

**Why this matters:** You are showing a logical sequence, not a random list of issues. Interviewers want to see that you know how to triage.

---

## How Screaming Frog Was Used

If asked specifically about your Screaming Frog process, cover these three areas:

### Configuration

> "I configured it with Googlebot user agent so I was seeing the site the same way Google does. I also turned on the PageSpeed API and set up custom extraction to check for schema markup presence, since the default Screaming Frog reports don't tell you whether JSON-LD is implemented or not."

### Prioritisation from Crawl Data

> "The crawl gave me a ranked list of issues by volume, but volume alone doesn't determine priority. A single robots.txt line blocking two suburb pages is a higher priority than 40 images missing alt text, even though the images represent a bigger raw number. I used the crawl data as input into a priority scoring matrix rather than working through it line by line."

### Cross-Referencing with GSC

> "Screaming Frog tells you what the site looks like from a crawling perspective. GSC tells you how Google is actually treating those pages. The two have to be read together. For example, Screaming Frog showed the suburb pages were crawlable - they returned 200 status. But GSC Coverage showed they were not indexed. That combination told me the issue was content quality, not technical access. If the pages had been blocked in robots.txt, they would show up differently in both tools."

---

## How GSC Insights Influenced Priorities

This is often the most important part of the interview because it shows analytical ability beyond just running tools.

### The CTR Analysis Story

> "One of the most useful exercises I ran in GSC was a CTR gap analysis. I exported the performance data for pages ranking in positions 1-15 and compared their actual CTR against the expected CTR for their average position. Several pages were ranking in positions 4-6 but had CTRs of 1-2%, when you would normally expect 6-8% at that position. That told me the issue was not the ranking - it was the click appeal of the snippet in the results."

> "The hot water repair page was the clearest example. It ranked at position 4.2 on average but was getting 2.1% CTR. The title was 'Hot Water Repair | Apex Plumbing'. No location, no urgency, no differentiator. For a homeowner searching for someone to fix their hot water system today, that title gives them no reason to click over the competitors around it. Updating the title to include the location, same-day availability, and a 24/7 signal was a Phase 1 fix that required no developer involvement."

### The Unindexed Pages Story

> "The Coverage report showed 6 suburb pages in 'Crawled, currently not indexed.' In GSC Performance, I could see the domain was still getting impressions for those suburb-based queries - but the impressions were going to the homepage, not the suburb page. So traffic was landing on a generic page instead of a page specifically about plumbing in Riverside or Springfield. The fix required both removing the robots.txt block for two pages and improving the content depth on all six pages."

### How It Changed the Sequence of Fixes

> "Without GSC data, I might have prioritised the redirect chain cleanup first based on volume. But GSC told me the 6 unindexed suburb pages and the robots.txt block were the issues most directly costing the business traffic right now. The redirect chains were causing inefficiency and link equity dilution, but they were not blocking indexation. So the robots.txt fix went first, then title tag updates, then redirect cleanup."

---

## How Fixes Were Sequenced

This is where you demonstrate strategic thinking and business awareness.

### Lead with the Principle

> "I sequenced fixes using three criteria: SEO impact, business revenue impact, and implementation effort. A high-impact fix that takes 10 minutes beats a medium-impact fix that takes two weeks, especially in the first phase when momentum and quick wins matter."

### Explain the Phase Structure

> "Phase 1 was reserved for anything that was either blocking indexation or required a single low-effort change for high return. The robots.txt fix, the GBP category update, and adding location modifiers to the title tags all fit that profile. None of them required a content writer or a developer for more than a few hours."

> "Phase 2 was content and schema - things that required more time and skill but directly addressed the core ranking weakness on the service pages. Schema markup had zero implementation on the site, so adding LocalBusiness and Service schema was a meaningful upgrade even though it required developer time."

> "Phase 3 was structural improvements - breadcrumbs, internal linking architecture, FAQ sections. These compound over time but don't produce overnight results, so they go in the later phase once the crawlability and content foundations are solid."

### Connecting Fixes to Outcomes

> "The reason the sequencing matters is because early wins keep the client or team engaged. If you spend month one on image compression and alt text, nothing visible changes in rankings or traffic. If you spend month one fixing the robots.txt block and updating title tags, you can show improved indexation in GSC within 3-4 weeks and a CTR improvement within 6 weeks. That builds trust and justifies the longer Phase 2 and 3 work."

---

## Handling Difficult Interview Questions

### "How do you know your fixes actually made a difference?"

> "I compared pre-fix and post-fix GSC data for the specific pages and keywords I targeted. For example, after the robots.txt fix and title tag updates, the suburb service pages moved from 'Crawled, not indexed' to 'Indexed' in GSC Coverage within 5 weeks. For the hot water repair page, I tracked the CTR week over week in GSC Performance and noted the improvement against the specific date the title tag was updated. Attribution is never perfect in SEO, but relating fix dates to metric changes is the clearest evidence available."

### "Why Screaming Frog over Sitebulb or other crawlers?"

> "Screaming Frog is my default for client sites because the reporting is granular, the export format is clean, and I can customise the crawl configuration precisely. Sitebulb has a better visual interface and can be more accessible for sharing with non-technical stakeholders. For this project I used Screaming Frog because the key outputs I needed were all available via export and the priority was speed and accuracy of the data, not presentation."

### "What would you have done differently?"

> "I would set up rank tracking before the audit starts rather than using GSC historical data to reconstruct pre-fix positions. GSC average position is a useful proxy but it averages across all queries for a URL. A dedicated rank tracker gives you position data for each individual target keyword, which makes post-fix attribution much cleaner."

---

## Key Talking Points to Always Include

Regardless of which specific question is asked, these are the points that demonstrate the most depth:

1. **You started with GSC before Screaming Frog** - shows you value real-world data over crawl assumptions
2. **You used a prioritisation framework, not just a checklist** - shows business and strategic thinking
3. **You connected Screaming Frog findings to GSC data** - shows you understand the two tools as complementary, not redundant
4. **You can explain why each fix came before another fix** - shows sequencing logic and project management ability
5. **You know the difference between a ranking problem and a CTR problem** - shows diagnostic depth
6. **You flagged a GBP issue as part of the audit scope** - shows understanding of local SEO as a broader discipline beyond just on-page

---

## Elevator Pitch Version (60 Seconds)

Use this if asked to describe the project quickly.

> "I ran a full local SEO audit for a home services business using Screaming Frog and Google Search Console. The site had declining organic traffic despite no known changes. I found the core issues were a robots.txt block introduced during a theme migration that was preventing two suburb service pages from being indexed, duplicate and template-built content on six other suburb pages that Google had chosen not to index, and title tags with no location modifiers on most service pages. I used GSC Coverage and Performance data to prioritise: the robots.txt fix and GBP category update went first because they were low effort and high return. Content improvements and schema implementation followed. The roadmap was documented as a phased fix backlog with an owner and status column so the dev and content team could work in parallel."

---

*Interview Guide version 1.0 | Local SEO Audit Portfolio | 2026*
