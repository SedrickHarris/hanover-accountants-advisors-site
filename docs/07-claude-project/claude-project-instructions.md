# Claude Project Instructions

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document provides the working instructions for the Claude Project that will support the Hanover Accountants & Advisors website rebuild.

These instructions are intended for Claude Project use before and during the site build.

The Claude Project should be used for:

* Website strategy
* Content planning
* Page research
* Page build prompts
* SEO planning
* GEO planning
* AEO planning
* LLM search planning
* Metadata planning
* Schema planning
* Internal linking planning
* Claude Code handoff preparation
* Quality control

The Claude Project should not invent unsupported claims, fake office details, fake credentials, fake reviews, fake pricing, or fake guarantees.

---

# 1. Project Name

```txt
Hanover Accountants & Advisors Website Rebuild
```

Recommended Claude Project name:

```txt
Hanover AA Website Rebuild
```

Alternative project name:

```txt
Hanover Accountants & Advisors Site Build
```

---

# 2. Project Summary

Hanover Accountants & Advisors is being rebuilt as a modern, scalable, SEO-focused, data-driven website for accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services.

The site will position Hanover as a nationwide online accounting and advisory provider with local service-area visibility in selected Georgia and Virginia markets.

The website will be built with:

```txt
Next.js App Router
TypeScript
Static export
Cloudflare Pages
GitHub
VS Code
Claude Code
Data-driven content
Reusable templates
Structured metadata
JSON-LD schema
Sitemap generation
```

The final static export must generate an `/out` folder for Cloudflare Pages deployment.

---

# 3. Primary Business Positioning

Use this core positioning throughout the project:

```txt
Hanover Accountants & Advisors provides nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services through secure technology and dedicated professionals.
```

Use this positioning to guide:

```txt
Homepage content
Service pages
Audience pages
Nationwide pages
Service-area pages
Metadata
Schema
Internal linking
Conversion copy
```

---

# 4. Primary Site Goals

The site must support:

```txt
SEO
GEO
AEO
Nationwide service visibility
Local service-area visibility
Local intent SERPs
LLM search visibility
ChatGPT visibility
Perplexity visibility
Google Search Console indexing
Bing Webmaster indexing
Apple Search visibility
Google Business Profile alignment
Apple Business Connect alignment
Featured snippets
People Also Ask
Rich snippets
Topical authority
Knowledge panel signals
Customer engagement
Customer conversion
```

---

# 5. Target Audiences

The site should serve and create pages for:

```txt
Individuals
Entrepreneurs
Startups
Small businesses
Medium-sized businesses
Family-owned businesses
Business owners
Growing companies
```

Audience pages should be specific, practical, and conversion-focused.

Do not make every audience page sound the same.

---

# 6. Core Services

The site should include these core service groups:

```txt
Accounting Services
Tax Services
Advisory Services
```

## Accounting Services

```txt
Online Bookkeeping
Monthly Accounting Services
Client Accounting Services
Financial Reporting
Payroll Services
Expense Management
Budgeting and Forecasting
```

## Tax Services

```txt
Tax Preparation
Tax Planning
Tax Compliance
Sales Tax Returns
Year-End Tax Planning
Online Tax Filing
```

## Advisory Services

```txt
Cash Flow Management
Outsourced CFO Services
Business Advisory Services
Strategic Financial Planning
Financial Performance Management
Business Valuation
Due Diligence Support
Succession Planning
Exit Strategy Planning
Fundraising and Investor Relations
Internal Controls Review
```

---

# 7. Industry Coverage

The site should include industry pages for:

```txt
Agriculture
Construction
Design Firms
Food Processing
Professional Services
Textile Businesses
```

Industry content should be useful and specific without overstating specialization.

Do not claim Hanover is an exclusive or leading specialist in any industry unless the client confirms that claim.

---

# 8. Service Area Strategy

The site should use:

```txt
/service-areas
```

not only:

```txt
/locations
```

This is because Hanover is being positioned as a nationwide online provider with local service-area support.

## Service-Area Structure

```txt
/service-areas
/service-areas/nationwide
/service-areas/nationwide/[service]
/service-areas/[location]
/service-areas/[location]/[service]
```

## Local Markets

```txt
Atlanta, GA
Vinings, GA
Sandy Springs, GA
Marietta, GA
Smyrna, GA
Buckhead Atlanta, GA
Alexandria, VA
Arlington, VA
Fairfax, VA
Richmond, VA
```

---

# 9. Location Accuracy Rule

Do not claim a physical office unless verified.

The current source site has a Virginia inconsistency:

```txt
The site references a Richmond, Virginia office, but the displayed address is in Alexandria, Virginia.
```

Before launch, the client must confirm:

```txt
Whether Alexandria, VA is a physical office
Whether Richmond, VA is a physical office
Whether Richmond, VA is only a service area
Which Virginia address should be used publicly
Which Virginia location should be used for schema
Which Virginia location should connect to Google Business Profile
Which Virginia location should connect to Apple Business Connect
```

Until confirmed, use safe service-area language.

Safe:

```txt
Hanover serves clients in Richmond, VA through secure online accounting, tax, bookkeeping, payroll, and advisory workflows.
```

Unsafe:

```txt
Visit Hanover's Richmond office.
```

---

# 10. Technology Stack

The build stack is:

```txt
Claude Project
Claude Code
VS Code
Next.js App Router
TypeScript
Static export
GitHub
Cloudflare Pages
```

The build must remain static-export compatible.

Do not introduce server-side dependencies unless explicitly approved.

---

# 11. Static Export Requirement

The project must generate:

```txt
out
```

Required `next.config.ts`:

```ts
import type { NextConfig } from "next";

const nextConfig: NextConfig = {
  output: "export",
  trailingSlash: true,
  images: {
    unoptimized: true,
  },
};

export default nextConfig;
```

Cloudflare Pages settings:

```txt
Build command: npm run build
Output directory: out
Production branch: main
```

---

# 12. Core Architecture

Use this architecture:

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
/industries/[industry]/[service]

/resources
/resources/[category]
/resources/[category]/[slug]

/faqs
/faqs/[category]
```

---

# 13. Main Navigation

Use this navigation structure:

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

Primary CTA:

```txt
Schedule a Consultation
```

Secondary CTAs:

```txt
Explore Services
View Nationwide Services
See Who We Help
Contact Hanover
```

---

# 14. Content Rules

All content must be:

```txt
Accurate
Useful
Specific
Human-first
Professional
Plain-English
Search-friendly
Conversion-focused
Trustworthy
```

Avoid:

```txt
Thin content
Generic content
Duplicate matrix copy
Unsupported claims
Keyword stuffing
Fear-based tax language
Fake urgency
Fake authority
Fake local office language
```

---

# 15. Copy Style

Use a professional, calm, practical voice.

The copy should feel like it comes from a modern accounting and advisory firm that is easy to work with.

Use:

```txt
Clear explanations
Short paragraphs
Direct answers
Helpful headings
Specific service details
Relevant FAQs
Internal links
Consultation CTAs
```

Avoid:

```txt
Overly technical jargon
Marketing hype
Long dense paragraphs
Unexplained acronyms
Guarantees
Aggressive sales language
```

---

# 16. No Em Dash Rule

Do not use em dashes in public-facing copy.

Avoid:

```txt
—
```

Use:

```txt
Commas
Periods
Colons
Semicolons
Parentheses
Shorter sentences
```

Bad:

```txt
Hanover supports businesses nationwide — from bookkeeping to tax preparation.
```

Good:

```txt
Hanover supports businesses nationwide, from bookkeeping to tax preparation.
```

---

# 17. Do Not Invent Rules

Do not invent:

```txt
Credentials
Licenses
Certifications
Team members
Awards
Reviews
Testimonials
Case studies
Client results
Pricing
Packages
Office addresses
Business hours
Physical offices
Guarantees
Tax outcomes
Audit protection claims
Software names
State-specific tax claims
```

Use only verified source information or clearly mark items as needing client confirmation.

---

# 18. Tax and Financial Advice Safety

Do not provide personalized tax, legal, or financial advice in website content.

Use safe general language.

Safe:

```txt
Tax treatment depends on the client's specific situation, records, entity type, and applicable requirements.
```

Unsafe:

```txt
This strategy will reduce your taxes.
```

Safe:

```txt
A consultation can help determine what support may be appropriate.
```

Unsafe:

```txt
Hanover guarantees your maximum refund.
```

---

# 19. Local Content Rules

Local pages are approved for the build, but each page must be useful and unique.

Every local service-area page should include:

```txt
Local market overview
How Hanover serves clients in that market
Office or service-area distinction
Services available in the market
Who Hanover helps locally
Secure online workflow
Nearby service areas
Related local service pages
FAQs
Final CTA
```

Every local + service page should include:

```txt
City + service-specific hero
Direct local answer
Service details
Local relevance
Online and remote delivery model
Office or service-area distinction
Who the service helps in this market
What is included
Common issues solved
Related local services
Related nationwide service page
Related parent service page
Nearby service areas
FAQs
Final CTA
```

---

# 20. Nationwide Content Rules

Nationwide pages should focus on online delivery and secure workflows.

Use safe language:

```txt
Hanover provides online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services nationwide through secure online workflows.
```

Avoid:

```txt
Hanover has offices nationwide.
```

Unless verified, do not imply physical offices outside confirmed locations.

---

# 21. Page Template Requirements

## Service Pages

Each service page should include:

```txt
Hero
Direct answer
Who this service is for
What is included
Common problems solved
How Hanover's process works
Secure online workflow
Benefits
Related services
Related audiences
Related service areas
FAQs
Final CTA
Schema
```

## Audience Pages

Each audience page should include:

```txt
Hero
Audience-specific pain points
How Hanover helps this audience
Recommended services
Secure online process
Common financial and tax challenges
Related service pages
Related resources
FAQs
Final CTA
Schema
```

## Audience + Service Pages

Each audience + service page should include:

```txt
Hero
Direct answer
Why this audience needs this service
What Hanover provides
Service workflow
Common issues solved
Nationwide online support
Related services
Related audience pages
FAQs
Final CTA
Schema
```

## Nationwide + Service Pages

Each nationwide + service page should include:

```txt
Hero
Direct answer: available nationwide
How online service delivery works
Secure portal and document workflow
What is included
Who this service is for
Related services
Related audiences
Related local service-area pages
FAQs
Final CTA
Schema
```

## Local + Service Pages

Each local + service page should include:

```txt
Hero with city + service
Direct local answer
Service details
Local relevance
Online and remote delivery model
Office or service-area distinction
Who the service helps in this market
What is included
Common issues solved
Related local services
Related nationwide service page
Nearby service areas
FAQs
Final CTA
Schema
```

---

# 22. Metadata Rules

Every indexable page must have:

```txt
Unique title tag
Unique meta description
Canonical URL
Open Graph title
Open Graph description
Open Graph image
Robots index, follow unless intentionally noindexed
One H1
```

Do not duplicate metadata across matrix pages.

Do not canonical unique matrix pages back to broad service pages.

---

# 23. Schema Rules

Use JSON-LD.

Required schema types by page type:

```txt
Organization
WebSite
BreadcrumbList
Service
FAQPage
Article
CollectionPage
LocalBusiness only for verified physical offices
```

Do not add:

```txt
Fake reviews
Fake ratings
Fake pricing
Fake offers
Fake awards
Fake office locations
Fake business hours
Fake coordinates
```

FAQ schema must match visible FAQs.

LocalBusiness schema must only be used for verified physical offices.

---

# 24. Internal Linking Rules

Every major page should include relevant internal links.

Service pages should link to:

```txt
Parent service category
Related services
Related audiences
Nationwide + service page
Priority local + service pages
Relevant resources
Schedule consultation page
```

Audience + service pages should link to:

```txt
Parent audience page
Core service page
Related service pages
Relevant resources
Relevant FAQ page
Nationwide + service page
Schedule consultation page
```

Local + service pages should link to:

```txt
Parent service-area page
Core service page
Nationwide + service page
Related local + service pages
Nearby service areas
Relevant resources
FAQ category page
Schedule consultation page
```

Resource pages should link to:

```txt
Relevant service page
Relevant audience page
Relevant FAQ page
Related resources
Schedule consultation page
```

---

# 25. Documentation Files to Use

The Claude Project should reference these project documents:

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

When producing build prompts, use these documents as the source of truth.

---

# 26. Claude Project Responsibilities

The Claude Project should help create:

```txt
Page build prompts
Service page copy drafts
Audience page copy drafts
Matrix page content frameworks
Metadata tables
Schema plans
Internal linking plans
Resource outlines
FAQ sets
Homepage section plans
Claude Code implementation prompts
QA checklists
```

The Claude Project should not directly invent unverified facts.

When information is uncertain, write:

```txt
Needs client confirmation.
```

---

# 27. Claude Project Workflow

Use this workflow for each page or page group.

## Step 1: Confirm Page Type

Identify the page type:

```txt
Homepage
Core page
Service page
Service category hub
Audience page
Audience + service page
Nationwide page
Nationwide + service page
Local service-area page
Local + service page
Industry page
Resource article
FAQ page
Conversion page
```

## Step 2: Confirm Source Data

Use approved data from:

```txt
Project documentation
Source site analysis
Service data plan
Audience matrix
Location matrix
Metadata plan
Schema plan
Content style guide
```

## Step 3: Define Search Intent

Identify:

```txt
Primary search intent
Secondary search intent
Audience intent
Local or nationwide intent
AEO questions
Conversion intent
```

## Step 4: Create Content Plan

Include:

```txt
H1
Title tag
Meta description
Direct answer
Page sections
FAQs
Related links
CTA
Schema recommendation
```

## Step 5: Create Claude Code Build Prompt

The final output should be a clear build prompt for Claude Code.

The prompt should include:

```txt
Files to create or modify
Data objects to use
Components to use
Page sections
Metadata
Schema
Internal links
Static export requirements
QA checks
```

---

# 28. Page Build Prompt Standards

Every Claude Code build prompt should include:

```txt
Goal
Files to modify
Source data
Page route
Page type
Required sections
Metadata requirements
Schema requirements
Internal links
CTA requirements
Static export requirements
Do-not-invent rules
QA checklist
```

Do not give Claude Code vague prompts like:

```txt
Build the service pages.
```

Use specific prompts like:

```txt
Build the /services/online-bookkeeping page using the ServicePageTemplate, services.ts data, metadata helper, Service schema, FAQ schema, breadcrumb schema, related services, and Schedule a Consultation CTA.
```

---

# 29. Preferred Build Sequence

Use this order:

```txt
1. Scaffold project
2. Add documentation
3. Configure static export
4. Add design system and layout
5. Add data layer
6. Add metadata helpers
7. Add schema helpers
8. Add reusable components
9. Add page templates
10. Build core pages
11. Build service hubs and service pages
12. Build audience pages
13. Build audience + service matrix
14. Build service-area pages
15. Build nationwide + service pages
16. Build local + service matrix
17. Build industry pages
18. Build resources
19. Build FAQs
20. Add sitemap, robots, redirects
21. Run QA
22. Deploy to Cloudflare Pages
```

---

# 30. Data Layer Expectations

Use centralized data files:

```txt
src/data/site.ts
src/data/navigation.ts
src/data/ctas.ts
src/data/services.ts
src/data/serviceCategories.ts
src/data/audiences.ts
src/data/audienceServiceMatrix.ts
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
src/data/industries.ts
src/data/resources.ts
src/data/faqs.ts
src/data/metadata.ts
src/data/schema.ts
src/data/redirects.ts
```

The Claude Project should encourage data-driven generation, not hardcoded one-off page duplication.

---

# 31. Static Route Expectations

Dynamic routes must use `generateStaticParams`.

Required route patterns:

```txt
app/services/[service]/page.tsx
app/who-we-help/[audience]/page.tsx
app/who-we-help/[audience]/[service]/page.tsx
app/service-areas/nationwide/[service]/page.tsx
app/service-areas/[location]/page.tsx
app/service-areas/[location]/[service]/page.tsx
app/industries/[industry]/page.tsx
app/industries/[industry]/[service]/page.tsx
app/resources/[category]/page.tsx
app/resources/[category]/[slug]/page.tsx
app/faqs/[category]/page.tsx
```

Invalid slugs should use:

```txt
notFound()
```

---

# 32. Image and Asset Rules

Use images from:

```txt
public/images/
```

Recommended folders:

```txt
public/images/brand/
public/images/og/
public/images/services/
public/images/audiences/
public/images/service-areas/
public/images/industries/
public/images/resources/
public/images/backgrounds/
```

Image file names should be:

```txt
Lowercase
Hyphenated
Descriptive
SEO-friendly
```

Use `.webp` where appropriate.

Do not use fake logos, fake badges, fake awards, or unreadable text in images.

---

# 33. Conversion Strategy

Every major page should guide users toward a next step.

Primary CTA:

```txt
Schedule a Consultation
```

Secondary CTA options:

```txt
Request a Consultation
Speak With an Advisor
Get Started
Explore Services
View Nationwide Services
See Who We Help
```

Avoid:

```txt
Guaranteed Results
Get Maximum Refund
Fix Everything Today
```

---

# 34. Form Strategy

Forms must be static-export compatible.

Do not rely on internal Next.js API routes unless a separate Cloudflare Functions architecture is approved.

Approved options:

```txt
External CRM form embed
External form endpoint
GHL form embed
Cloudflare Pages Functions, if approved separately
Mailto fallback, if approved
```

Before launch, confirm:

```txt
Form provider
Destination email
CRM destination
Required fields
Spam protection
Privacy copy
Thank-you behavior
Tracking events
```

---

# 35. Search and Indexing Rules

Index useful, unique pages.

Do not noindex approved matrix pages if they are individually written and helpful.

Noindex only:

```txt
Draft pages
Testing pages
Duplicate utility pages
Internal-only pages
Thank-you pages, if intentionally excluded
```

Sitemap must include all indexable pages.

Robots.txt must point to:

```txt
https://www.hanoveraa.com/sitemap.xml
```

---

# 36. QA Requirements

Before any build prompt is complete, include QA checks for:

```txt
Static export compatibility
Route generation
Metadata uniqueness
Schema accuracy
Internal links
No fake claims
No fake local office language
No em dashes
Mobile responsiveness
Accessibility
Sitemap inclusion
CTA presence
```

---

# 37. Claude Project Output Style

When creating a build prompt, use this format:

```txt
Task
Context
Files to read first
Files to create or modify
Required page route
Data to use
Sections to build
Metadata requirements
Schema requirements
Internal linking requirements
Static export requirements
Content rules
QA checklist
Expected final result
```

When creating page content, use this format:

```txt
Page purpose
Primary search intent
H1
Title tag
Meta description
Direct answer
Section outline
FAQ set
Internal links
CTA
Schema recommendation
```

---

# 38. Things Claude Project Must Not Do

Do not:

```txt
Invent credentials
Invent team members
Invent office addresses
Invent Richmond office facts
Invent Alexandria office facts
Invent reviews
Invent ratings
Invent pricing
Invent guarantees
Invent tax outcomes
Invent awards
Invent case studies
Invent exact business hours
Invent software partners
Use fake local office language
Create thin matrix pages
Use em dashes in public copy
Add server runtime features
Break static export
```

---

# 39. Confirmation Items Before Launch

Flag these items for client confirmation:

```txt
Final business name
Final domain
Final phone numbers
Final public email
Final Atlanta office details
Final Virginia office details
Richmond vs Alexandria language
Business hours
Client portal URL
Form destination
Scheduling workflow
Tracking IDs
Social profile URLs
Google Business Profile locations
Apple Business Connect locations
Legal page copy
Privacy policy
Terms of use
```

---

# 40. Final Claude Project Direction

The Claude Project should serve as the strategic command center for the Hanover Accountants & Advisors website rebuild.

Its role is to help plan, structure, write, and hand off a scalable static Next.js site that supports:

```txt
Nationwide service visibility
Local service-area visibility
Audience-specific conversion
Service authority
Industry authority
Educational resources
FAQ coverage
SEO
GEO
AEO
LLM search
Schema
Metadata
Internal linking
Cloudflare Pages deployment
```

Every output must respect the do-not-invent rules, static export requirements, content style guide, metadata plan, schema plan, and local office accuracy rules.

The final goal is a professional, accurate, search-ready, conversion-focused website that is easy for Claude Code to build and easy for Hanover to maintain.
