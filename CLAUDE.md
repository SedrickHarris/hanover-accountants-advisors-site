# CLAUDE.md

## Project Name

Hanover Accountants & Advisors Website Rebuild

## Project Type

Nationwide accounting, tax, bookkeeping, payroll, and advisory website rebuild with local service-area expansion.

## Primary Build Goal

Build a modern, scalable, SEO-ready, GEO-ready, AEO-ready, LLM-search-ready website for Hanover Accountants & Advisors using Next.js, TypeScript, GitHub, and Cloudflare Pages.

The website must position Hanover as a nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory firm while preserving and expanding local service-area visibility for Georgia and Virginia markets.

## Tech Stack

Use the following stack:

```txt
Claude Project
Claude Code
VS Code
Next.js
TypeScript
React
GitHub
Cloudflare Pages
Static export using /out
```

## Hosting Requirement

The site will be hosted on Cloudflare Pages.

The Next.js project must support static export.

Required `next.config.ts` pattern:

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

Expected Cloudflare Pages output directory:

```txt
out
```

## Core Positioning

Hanover Accountants & Advisors provides nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services through secure technology and dedicated professionals.

The site should make national availability clear while also supporting local service-area pages.

Core positioning language:

```txt
Nationwide online accounting, tax, bookkeeping, payroll, and advisory services for individuals, entrepreneurs, startups, small businesses, family-owned businesses, business owners, and growing companies.
```

## Verified Service Foundation

The current site supports these service categories and concepts:

```txt
Advisory services
Tax services
Online bookkeeping
Accounting services
Monthly bookkeeping
Client accounting services
Financial reporting
Payroll services
Tax preparation
Tax compliance
Sales tax returns
Expense management
Budgeting and forecasting
Cash flow management
Outsourced CFO services
Business advisory services
Strategic financial planning
Financial performance management
Business valuation
Due diligence support
Succession planning
Exit strategy planning
Fundraising and investor relations
Secure client portal workflow
Secure document upload
E-signature
E-filing
```

Do not remove or weaken these service categories.

## Target Audiences

Build content and routes for:

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

## Target Industries

Build content and routes for:

```txt
Agriculture
Construction
Design firms
Food processing
Professional services
Textile businesses
```

## Service Area Strategy

Use `/service-areas` as the primary service-area structure.

Do not use only `/locations`, because Hanover is being positioned as a nationwide service provider.

Primary structure:

```txt
/service-areas
/service-areas/nationwide
/service-areas/nationwide/[service]
/service-areas/[location]
/service-areas/[location]/[service]
```

Core service-area pages:

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

## Location Accuracy Rule

The current site appears to include inconsistent Virginia location language.

Do not claim Richmond is a physical office unless confirmed.

Do not claim Alexandria is the same as Richmond.

Until clarified, treat Virginia pages carefully:

```txt
Alexandria, VA may be a physical office if confirmed.
Richmond, VA may be a service area unless a physical office is confirmed.
Arlington, VA and Fairfax, VA should be treated as service areas unless physical offices are confirmed.
```

Use physical office language only when verified.

Use service-area language for served markets without a confirmed office.

## Core Site Architecture

Build toward this structure:

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

## Main Navigation

Use this main navigation unless instructed otherwise:

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

Do not place every local page in the main navigation.

Use dropdowns, hub pages, related links, footer links, HTML sitemap, and XML sitemap for discovery.

## Content Rules

Every page must be useful, specific, and built for humans first.

Do not create thin content.

Do not create city-name swap pages.

Do not create duplicate local pages.

Do not create generic service pages that only repeat the same structure without unique value.

Each service, audience, local, nationwide, industry, resource, and FAQ page must include page-specific value.

## Local Page Content Rule

Every local page must include unique content for that location.

Local pages should include:

```txt
Local market overview
How Hanover serves that area
Office or service-area distinction
Relevant services for that market
Who Hanover helps in that market
Nearby service areas
Related local service pages
Nationwide service connection
Local FAQs
Clear consultation CTA
Appropriate schema
```

## Local + Service Page Content Rule

Every local + service page must include unique content for that location and service combination.

Local + service pages should include:

```txt
City + service-specific hero
Direct local answer
Service-specific explanation
Local business relevance
Online and remote delivery model
Who the service helps in that area
What is included
Related local services
Related nationwide service page
FAQs
Final CTA
Schema
```

## Audience + Service Page Content Rule

Every audience + service page must include unique content for that audience and service combination.

Audience + service pages should include:

```txt
Audience-specific hero
Direct answer
Why this audience needs this service
Common financial, accounting, tax, payroll, or advisory challenges
What Hanover provides
Secure online workflow
Related services
Related audience pages
Related resources
FAQs
Final CTA
Schema
```

## Nationwide Service Page Content Rule

Every nationwide + service page must clearly explain how Hanover provides that service online across the United States.

Nationwide service pages should include:

```txt
Nationwide service headline
Direct answer
How online service delivery works
Secure portal workflow
What is included
Who this service is for
Related services
Related audiences
Related local service-area pages
FAQs
Final CTA
Schema
```

## SEO, GEO, AEO, and LLM Rules

The site must support:

```txt
SEO
GEO
AEO
Local intent SERPs
Nationwide service intent
LLM search visibility
ChatGPT discovery
Perplexity discovery
Google Search Console visibility
Bing Webmaster indexing
Apple Search visibility
Google Business Profile support
Featured snippets
People Also Ask
Rich snippets
Knowledge panel signals
Topical authority
Customer engagement
Customer conversion
```

Each major page should include:

```txt
Clear H1
Direct answer section near the top
Readable section hierarchy
Internal links
FAQs
Schema
Conversion CTA
Related pages
Plain-English explanations
```

## Metadata Rules

Every page needs:

```txt
Unique title tag
Unique meta description
Single H1
Logical H2 and H3 structure
Canonical URL
Open Graph title
Open Graph description
Clean slug
Relevant internal links
```

Do not duplicate title tags or meta descriptions across matrix pages.

## Schema Rules

Use schema accurately.

Global schema types:

```txt
Organization
AccountingService
ProfessionalService
WebSite
SiteNavigationElement
BreadcrumbList
```

Service pages:

```txt
Service
FAQPage
BreadcrumbList
```

Nationwide service pages:

```txt
Service
Organization
AreaServed: United States
FAQPage
BreadcrumbList
```

Verified physical office pages only:

```txt
LocalBusiness
ProfessionalService
PostalAddress
OpeningHoursSpecification
BreadcrumbList
```

Service-area pages without a verified office:

```txt
Service
AreaServed
FAQPage
BreadcrumbList
```

Resource pages:

```txt
Article
BlogPosting
FAQPage where relevant
BreadcrumbList
```

Do not use LocalBusiness schema for cities without a verified office.

Do not create fake review schema.

Do not create fake aggregate ratings.

Do not invent business hours.

Do not invent coordinates.

## Internal Linking Rules

Use internal links intentionally.

Recommended link patterns:

```txt
Service page -> service category hub
Service page -> related service pages
Service page -> audience pages
Service page -> nationwide service page
Service page -> priority local service pages
Service page -> relevant resources
Service page -> contact or consultation CTA

Audience page -> audience + service pages
Audience + service page -> core service page
Audience + service page -> audience hub
Audience + service page -> relevant resources
Audience + service page -> consultation CTA

Service-area page -> location + service pages
Location + service page -> core service page
Location + service page -> nationwide service page
Location + service page -> related local services
Location + service page -> nearby service areas

Resource page -> relevant service page
Resource page -> relevant audience page
Resource page -> related resources
Resource page -> consultation CTA
```

## Conversion Rules

Every major page must include a clear conversion path.

Primary CTAs:

```txt
Schedule a Consultation
Request a Consultation
Speak With an Advisor
Get Started
```

Secondary CTAs:

```txt
Explore Services
View Nationwide Services
See Who We Help
Learn How Online Accounting Works
```

Do not overload pages with too many competing CTAs.

## Voice and Tone

Use a professional, clear, trustworthy accounting and advisory tone.

Voice should be:

```txt
Clear
Professional
Helpful
Plain-English
Confident
Accurate
Practical
Trustworthy
Human
```

Avoid:

```txt
Hype
Overpromising
Fear-based language
Unsupported claims
Buzzword stuffing
Keyword stuffing
Fake urgency
Complex jargon without explanation
```

## Copy Formatting Rules

Use:

```txt
Short paragraphs
Clear headings
Scannable sections
Plain-English explanations
FAQ answers
Direct answers
Bullet lists when helpful
Conversion sections
```

Avoid em dashes in public-facing copy.

Use commas, periods, colons, or parentheses instead.

## Do Not Invent Rules

Never invent:

```txt
Credentials
Licenses
Certifications
Team member names
Awards
Reviews
Testimonials
Case studies
Client results
Pricing
Office addresses
Business hours
Physical offices
Guarantees
Tax outcomes
Audit protection claims
Years in business beyond verified source material
```

If a detail is not verified, leave it out or mark it as needing client confirmation.

## Build Style Rules

Use reusable components and a data-driven structure, but keep final page content unique.

Preferred structure:

```txt
src/data/services.ts
src/data/serviceCategories.ts
src/data/audiences.ts
src/data/audienceServiceMatrix.ts
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
src/data/industries.ts
src/data/resources.ts
src/data/faqs.ts
src/data/navigation.ts
src/data/schema.ts
src/data/ctas.ts
```

Preferred components:

```txt
Header
Footer
MobileNav
Breadcrumbs
Hero
DirectAnswer
ServiceGrid
AudienceGrid
ServiceAreaGrid
IndustryGrid
FAQSection
CTASection
RelatedLinks
ServiceCard
AudienceCard
LocationCard
IndustryCard
ResourceCard
JsonLd
```

## Next.js Requirements

Use App Router.

Use TypeScript.

Use static routes and `generateStaticParams` for dynamic routes.

Keep all routes compatible with static export.

Do not use server-only features that break Cloudflare Pages static export.

Do not use image optimization that requires a server.

Do not use API routes unless explicitly approved and compatible with deployment.

## Cloudflare Pages Rules

The build must produce:

```txt
/out
```

Use:

```bash
npm run build
```

Cloudflare settings should be:

```txt
Build command: npm run build
Output directory: out
```

## Git Rules

Use clear commits.

Recommended commit pattern:

```txt
Initialize Hanover site scaffold
Add project documentation
Add site architecture and data layer
Add core layout components
Add homepage
Add services hub and service templates
Add audience pages
Add service-area pages
Add schema and metadata
Add prelaunch SEO setup
```

Before committing:

```bash
npm run build
```

If linting is configured:

```bash
npm run lint
```

## Quality Rules

Before finalizing any build phase, check:

```txt
No broken internal links
No missing page titles
No duplicate metadata
No missing H1s
No fake office claims
No fake reviews
No thin local pages
No unverified claims
No Cloudflare export issues
No broken mobile navigation
No missing CTAs
No missing sitemap routes
No schema validation issues
```

## Priority Build Phases

### Phase 1: Foundation

Build:

```txt
Core pages
Main hubs
Priority service pages
Layout system
Navigation
Footer
Contact flow
Client portal link
Basic metadata
Basic schema
```

### Phase 2: Nationwide Authority

Build:

```txt
/service-areas/nationwide
/service-areas/nationwide/[service]
Nationwide content sections
Nationwide schema
Online workflow messaging
Secure portal messaging
```

### Phase 3: Audience Authority

Build:

```txt
/who-we-help
/who-we-help/[audience]
/who-we-help/[audience]/[service]
```

### Phase 4: Local Service-Area Authority

Build:

```txt
/service-areas/[location]
/service-areas/[location]/[service]
```

Every local page must be unique and individually written.

### Phase 5: Industry Authority

Build:

```txt
/industries
/industries/[industry]
Optional /industries/[industry]/[service]
```

### Phase 6: Resources and FAQs

Build:

```txt
/resources
/resources/[category]
/resources/[category]/[slug]
/faqs
/faqs/[category]
```

### Phase 7: Technical SEO and Launch QA

Build and verify:

```txt
robots.txt
sitemap.xml
HTML sitemap
redirects
canonical tags
metadata
schema
404 page
GSC readiness
Bing readiness
Cloudflare Pages deployment
Mobile QA
Performance QA
Form QA
```

## Final Instruction

Build the Hanover site as a scalable, trustworthy, nationwide-first accounting and advisory website with strong local service-area support.

Preserve verified business facts.

Do not invent claims.

Do not create thin pages.

Keep all pages useful, specific, well-linked, conversion-focused, schema-ready, and compatible with Cloudflare Pages static export.
