# Hanover Accountants & Advisors Website Rebuild

## Project Name

Hanover Accountants & Advisors Website Rebuild

## Recommended Repo Name

```txt
hanover-aa-site
```

> ⚠️ **Naming note:** The repo that was actually created is
> `hanover-accountants-advisors-site` (and the local folder uses the same name).
> The brief originally recommended `hanover-aa-site`. Reconcile before launch if a
> shorter name is desired.

## Project Summary

This project is a full website rebuild for Hanover Accountants & Advisors.

The new site will position Hanover as a nationwide online accounting, tax, bookkeeping, payroll, and advisory firm with strong local service-area visibility for Georgia and Virginia markets.

The website will be built to support national search intent, local service-area search intent, audience-specific search intent, rich snippets, AEO, GEO, LLM search visibility, Google Search Console, Bing Webmaster, Apple Search, Google Business Profile support, customer engagement, and customer conversion.

## Primary Positioning

Hanover Accountants & Advisors provides nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services through secure technology and dedicated professionals.

The site will also support local service-area visibility for Atlanta, Georgia, nearby Georgia markets, Alexandria, Virginia, nearby Virginia markets, and Richmond, Virginia if confirmed.

## Core Business Focus

The site build will focus on these service categories:

* Accounting services
* Online bookkeeping
* Monthly accounting services
* Client accounting services
* Financial reporting
* Payroll services
* Tax preparation
* Tax planning
* Tax compliance
* Sales tax returns
* Expense management
* Budgeting and forecasting
* Cash flow management
* Outsourced CFO services
* Business advisory services
* Strategic financial planning
* Financial performance management
* Business valuation
* Due diligence support
* Succession planning
* Exit strategy planning
* Fundraising and investor relations
* Internal controls review

## Target Audiences

The site will include pages for:

* Individuals
* Entrepreneurs
* Startups
* Small businesses
* Medium-sized businesses
* Family-owned businesses
* Business owners
* Growing companies

## Target Industries

The site will include industry pages for:

* Agriculture
* Construction
* Design firms
* Food processing
* Professional services
* Textile businesses

## Service Area Strategy

The site will use a nationwide-first service-area model.

Primary structure:

```txt
/service-areas
/service-areas/nationwide
/service-areas/nationwide/[service]
/service-areas/[city-state]
/service-areas/[city-state]/[service]
```

Primary service-area pages:

```txt
/service-areas/nationwide
/service-areas/atlanta-ga
/service-areas/vinings-ga
/service-areas/sandy-springs-ga
/service-areas/marietta-ga
/service-areas/smyrna-ga
/service-areas/buckhead-atlanta-ga
/service-areas/alexandria-va
/service-areas/arlington-va
/service-areas/fairfax-va
/service-areas/richmond-va
```

Important note: the current site references a Richmond, Virginia office while listing an Alexandria, Virginia address. This must be clarified before final local schema, Google Business Profile alignment, Apple Business Connect alignment, and office-location claims are finalized.

## Tech Stack

* Claude Project
* Claude Code
* VS Code
* Next.js
* TypeScript
* React
* GitHub
* Cloudflare Pages
* Static export using `/out`

## Deployment Target

Cloudflare Pages

Recommended static export settings:

```ts
const nextConfig = {
  output: "export",
  trailingSlash: true,
  images: {
    unoptimized: true,
  },
};

export default nextConfig;
```

Cloudflare Pages output directory:

```txt
out
```

## Project Goals

The website should support:

* SEO
* GEO
* AEO
* Local intent SERPs
* Nationwide service intent
* LLM search visibility
* ChatGPT discovery
* Perplexity discovery
* Google Search Console indexing
* Bing Webmaster indexing
* Apple Search visibility
* Google Business Profile support
* Featured snippets
* People Also Ask
* Rich snippets
* Knowledge panel signals
* Topical authority
* Customer engagement
* Customer conversion

## Core Site Architecture

```txt
/
/about
/contact
/schedule-consultation
/get-started
/client-portal
/services
/services/accounting
/services/tax
/services/advisory
/services/[service]
/who-we-help
/who-we-help/[audience]
/who-we-help/[audience]/[service]
/service-areas
/service-areas/nationwide
/service-areas/nationwide/[service]
/service-areas/[location]
/service-areas/[location]/[service]
/industries
/industries/[industry]
/resources
/resources/[category]
/resources/[category]/[slug]
/faqs
/faqs/[category]
```

## Page Build Philosophy

Every page should be built individually with useful, specific content.

Do not create thin location pages.

Do not create city-name swap pages.

Do not create fake local office claims.

Do not create fake reviews, fake credentials, fake awards, fake guarantees, fake pricing, or fake professional designations.

Every service, audience, location, and matrix page must include unique value, clear service context, relevant FAQs, internal links, conversion CTAs, and appropriate schema.

## Main Navigation

Recommended main navigation:

```txt
Services
Who We Help
Nationwide Services
Service Areas
Industries
Resources
About
Contact
```

## Primary CTAs

Use consistent conversion actions across the site:

```txt
Schedule a Consultation
Request a Consultation
Speak With an Advisor
Get Started
```

## Secondary CTAs

```txt
Explore Services
View Nationwide Services
See Who We Help
Learn How Online Accounting Works
```

## Local Development Commands

Install dependencies:

```bash
npm install
```

Run local development server:

```bash
npm run dev
```

Build static export:

```bash
npm run build
```

Expected export directory:

```txt
out
```

## Recommended First-Time Setup

Create the local folder:

```powershell
mkdir C:\Users\Welcome\Desktop\client-sites\hanover-aa-site
cd C:\Users\Welcome\Desktop\client-sites\hanover-aa-site
```

Initialize the Next.js project:

```bash
npx create-next-app@latest . --ts --app
```

Install dependencies:

```bash
npm install
```

Initialize Git:

```bash
git init
git add -A
git commit -m "Initial Hanover website scaffold"
```

Add GitHub remote after creating the repo:

```bash
git remote add origin https://github.com/SedrickHarris/hanover-aa-site.git
git branch -M main
git push -u origin main
```

## Recommended Documentation Folder

```txt
docs/
  00-project-control/
  01-research/
  02-strategy/
  03-seo-aeo-geo/
  04-brand-content/
  05-matrices/
  06-technical/
  07-claude-project/
  08-qa-launch/
```

## Required Project Documents

The project documentation set should include:

```txt
README.md
CLAUDE.md
project-overview.md
source-site-analysis.md
do-not-invent.md
full-build-list.md
url-slug-strategy.md
site-architecture.md
services-data-plan.md
audience-service-matrix.md
location-service-matrix.md
schema-plan.md
metadata-plan.md
content-style-guide.md
folder-structure.md
nextjs-static-export.md
cloudflare-pages-deployment.md
claude-project-instructions.md
claude-code-handoff-prompt.md
prelaunch-checklist.md
```

## Build Rules

1. Use the verified current site as the factual foundation.
2. Position Hanover as nationwide-first.
3. Keep all local service-area pages.
4. Build every local page with unique local content.
5. Use `/service-areas` rather than only `/locations`.
6. Use LocalBusiness schema only for verified physical office locations.
7. Use Service and AreaServed schema for service-area pages.
8. Build service pages, nationwide service pages, audience pages, audience + service pages, location pages, and location + service pages as distinct content types.
9. Use FAQ sections on all major service, audience, local, and resource pages.
10. Use internal links intentionally.
11. Use a clean, professional, trustworthy accounting and advisory voice.
12. Avoid unsupported claims.
13. Avoid thin content.
14. Avoid duplicate page patterns.
15. Keep the project compatible with Cloudflare Pages static export.

## Build Phases

### Phase 1: Foundation Launch

* Core pages
* Main hubs
* Priority service pages
* Initial navigation
* Brand and layout system
* Contact and consultation flows

### Phase 2: Nationwide Authority

* Nationwide service-area hub
* Nationwide + service pages
* Secure online workflow messaging
* National accounting, bookkeeping, tax, payroll, and advisory positioning

### Phase 3: Audience Authority

* Audience hub
* Audience pages
* Priority audience + service pages

### Phase 4: Local Service-Area Authority

* Local service-area hub
* Local market pages
* Location + service pages
* Local FAQs
* Local internal links
* Local schema rules

### Phase 5: Industry Pages

* Industry hub
* Core industry pages
* Optional industry + service expansion

### Phase 6: Resource and FAQ Hub

* Resource categories
* Educational articles
* FAQ categories
* AEO/PAA/featured snippet content

### Phase 7: Technical SEO and Launch QA

* Metadata
* Schema
* Sitemap
* Robots
* Redirects
* Canonicals
* 404 page
* Mobile QA
* Performance QA
* Form QA
* GSC setup
* Bing Webmaster setup
* Cloudflare Pages deployment

## Prelaunch Requirements

Before launch, confirm:

* Final business name formatting
* Final phone numbers
* Final email address
* Final office addresses
* Richmond vs Alexandria Virginia office language
* Whether Richmond is a real office, service area, or old copy issue
* Whether all listed local markets are approved service areas
* Whether Hanover wants pricing shown or hidden
* Whether any team bios, credentials, or certifications can be listed
* Whether client testimonials are approved for reuse
* Whether the client portal link remains the same
* Whether any third-party forms, scheduling tools, analytics, or CRM integrations are needed

## Notes for Claude Code

Claude Code should treat this repo as a structured, data-driven static Next.js site.

The content system should be reusable, but the copy for each final page must be unique, useful, and specific to that service, audience, industry, or service area.

Do not generate fake business claims.

Do not invent credentials.

Do not invent reviews.

Do not claim a physical office in a city unless it is verified.

Do not remove nationwide positioning.

Do not remove the local service-area strategy.

Do not break Cloudflare Pages static export compatibility.
