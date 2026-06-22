# Claude Code Handoff Prompt

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the handoff framework between Claude Project and Claude Code for the Hanover Accountants & Advisors website rebuild.

This is not a master prompt for Claude Code to independently build the full site.

Claude Project is responsible for:

```txt
Research
Page strategy
Content planning
Page copy
Metadata copy
Schema copy
FAQ copy
Internal linking strategy
SEO planning
GEO planning
AEO planning
LLM search planning
Build prompt creation
```

Claude Code is responsible for:

```txt
Implementing the approved build prompt
Creating or modifying files listed in the prompt
Building routes, components, templates, and data objects as instructed
Preserving the approved content exactly
Maintaining static export compatibility
Running build checks
Flagging conflicts or missing content
```

Claude Code must not independently research, rewrite, expand, shorten, improve, reorganize, or reinterpret the approved content.

The approved build prompt is the source of truth.

---

# 1. Core Workflow

The approved workflow is:

```txt
1. Claude Project researches the page or page group.
2. Claude Project creates the page strategy.
3. Claude Project writes or approves the content.
4. Claude Project defines metadata, schema, FAQs, internal links, and CTA copy.
5. Claude Project creates a specific build prompt for Claude Code.
6. Claude Code builds only what the approved prompt instructs.
7. Claude Code preserves all approved content verbatim.
8. Claude Code flags conflicts or missing content instead of inventing solutions.
9. Claude Code runs the required checks.
10. Claude Code reports what was built, what changed, and what needs review.
```

Claude Project is the strategist.

Claude Code is the builder.

---

# 2. Primary Rule

Claude Code must build the approved prompt exactly as provided.

Claude Code may implement layout, components, routing, data placement, metadata rendering, schema rendering, responsive behavior, accessibility improvements, and static export compatibility.

Claude Code must not change the approved words.

---

# 3. Verbatim Content Lock

Claude Code must treat all approved content inside the build prompt as locked content.

The build prompt is the source of truth.

Claude Code may build layout, components, routes, data objects, metadata fields, schema objects, styling, and responsive behavior as instructed, but it must not alter approved written content.

## Claude Code Must Not Change

Claude Code must not change, modify, summarize, expand, rewrite, paraphrase, rearrange, or improve:

```txt
Headlines
Subheadings
Hero copy
Body copy
Direct answer sections
Service descriptions
Audience descriptions
Location descriptions
Industry descriptions
Resource article copy
FAQ questions
FAQ answers
CTA labels
Button text
Navigation labels
Metadata titles
Meta descriptions
Schema text fields
Alt text
Form labels
Legal copy
Trust copy
Disclaimers
Internal link anchor text
```

## Verbatim Build Rule

If the build prompt provides exact copy, Claude Code must place that copy exactly as written.

This includes:

```txt
Capitalization
Punctuation
Spelling
Line breaks where specified
CTA wording
FAQ wording
Metadata wording
Schema wording
Alt text wording
Internal link anchor text
Navigation labels
```

## No Copy Editing Rule

Claude Code must not copyedit the prompt.

Claude Code must not:

```txt
Make the content sound better
Make the content shorter
Make the content longer
Make the content more SEO-friendly
Make the content more conversational
Add keywords
Remove repeated words
Rewrite headings
Change CTA wording
Change metadata wording
Change schema descriptions
Adjust local wording
Add new claims
Remove qualifiers
Clean up grammar unless explicitly instructed
Replace words with synonyms
```

## Formatting Exception

Claude Code may only adjust formatting when required to render the approved content correctly in the website layout.

Allowed formatting changes include:

```txt
Wrapping copy in JSX elements
Placing copy inside components
Converting approved lists into mapped arrays
Adding semantic HTML tags
Applying responsive layout classes
Adding spacing, cards, grids, columns, or sections
Adding accessible labels when instructed
```

Formatting changes must not change the words.

---

# 4. Missing Content Rule

If required copy is missing from the build prompt, Claude Code must not invent it.

Claude Code should add a clear TODO comment in the code:

```txt
TODO: Approved content needed from Claude Project.
```

Claude Code may also report:

```txt
Missing approved content for this section. Claude Project needs to provide final copy.
```

Claude Code must not fill missing content with placeholder marketing copy unless the prompt explicitly instructs it to use placeholder copy.

---

# 5. Conflict Rule

If the build prompt conflicts with project documentation, Claude Code should stop and flag the conflict instead of silently rewriting the content.

## Example Conflict

The build prompt says:

```txt
Visit our Richmond office.
```

But the project documentation says:

```txt
Richmond office status is unconfirmed.
```

Claude Code should not silently fix the copy.

Claude Code should flag:

```txt
CONTENT CONFLICT: Richmond office language conflicts with do-not-invent and location accuracy rules. Needs clarification from Claude Project.
```

## Conflict Types to Flag

Claude Code must flag conflicts involving:

```txt
Unverified physical office claims
Richmond vs Alexandria location language
Fake reviews
Fake ratings
Fake pricing
Fake guarantees
Unsupported credentials
Unsupported certifications
Unsupported tax outcomes
Unsupported business hours
Unsupported software claims
Metadata that conflicts with visible copy
Schema that conflicts with visible copy
Internal links to routes that do not exist
Page routes that conflict with the approved slug strategy
```

Claude Code should not resolve these conflicts independently unless the build prompt explicitly provides the resolution.

---

# 6. Do Not Invent Rule

Claude Code must not invent:

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
State-specific tax guarantees
Local rankings
Google Business Profile details
Apple Business Connect details
```

When uncertain, Claude Code should write:

```txt
Needs client confirmation.
```

or add a code TODO:

```txt
TODO: Needs client confirmation before launch.
```

---

# 7. Role Separation

## Claude Project Owns

```txt
Research
Strategy
Content
Copywriting
SEO intent
AEO questions
GEO planning
Metadata copy
Schema copy
FAQ copy
Internal link strategy
Page intent
Content hierarchy
Build prompt creation
```

## Claude Code Owns

```txt
Implementation
Routing
Components
Templates
Data placement
Static route generation
Static export compatibility
Responsive layout
Accessibility implementation
Schema rendering
Metadata rendering
Sitemap implementation
Robots file implementation
Redirect file implementation
Build validation
```

Claude Code is not the strategist or copywriter.

Claude Code is the implementation agent.

---

# 8. Required Handoff Format

Every Claude Project to Claude Code handoff should include this structure.

```txt
Task
Context
Files to read first
Files to create or modify
Page route or routes
Page type
Approved content
Metadata
Schema
Internal links
CTA requirements
Design and layout instructions
Static export requirements
Content lock rules
Do-not-invent rules
QA checklist
Expected final result
```

Claude Code should follow the handoff exactly.

---

# 9. Required Build Prompt Template

Use this template when Claude Project creates a build prompt for Claude Code.

```txt
Task:
Build [page or page group] for Hanover Accountants & Advisors.

Context:
This page has already been researched and planned in Claude Project. The copy, metadata, schema text, FAQs, CTAs, and internal link strategy below are approved. Build them verbatim.

Files to read first:
- README.md
- CLAUDE.md
- docs/do-not-invent.md
- docs/content-style-guide.md
- docs/site-architecture.md
- docs/metadata-plan.md
- docs/schema-plan.md
- docs/nextjs-static-export.md
- Relevant data files

Files to create or modify:
[List exact files]

Route:
[Exact route]

Page type:
[Service page, audience page, local + service page, resource article, etc.]

Approved content:
[Paste approved content. Claude Code must not rewrite.]

Metadata:
[Paste approved title tag, meta description, canonical, OG title, OG description, and H1. Claude Code must not rewrite.]

Schema:
[Paste schema requirements and approved text fields. Claude Code must not rewrite schema text fields.]

Internal links:
[Paste exact links and anchor text. Claude Code must not rewrite anchor text.]

CTA requirements:
[Paste exact CTA labels and destinations.]

Design and layout instructions:
[Describe layout, components, responsive behavior, and visual hierarchy.]

Static export requirements:
- Must remain compatible with output: "export".
- Must not use API routes.
- Must not use server actions.
- Must use generateStaticParams for dynamic routes.
- Must build into /out.

Content lock rules:
- Build approved copy verbatim.
- Do not rewrite, summarize, expand, shorten, improve, or copyedit content.
- Do not change metadata wording.
- Do not change FAQ wording.
- Do not change CTA labels.
- Do not change internal link anchor text.
- If content is missing, add a TODO instead of inventing copy.
- If content conflicts with project rules, flag the conflict.

Do-not-invent rules:
Do not invent credentials, reviews, pricing, office details, business hours, guarantees, tax outcomes, or local claims.

QA checklist:
[List exact QA checks]

Expected final result:
[Describe what should exist after implementation.]
```

---

# 10. Page Research Output Format for Claude Project

Before a build prompt is created, Claude Project should produce a page research and strategy output.

Use this format:

```txt
Page:
[Page name]

Route:
[Exact route]

Page type:
[Page type]

Primary intent:
[Primary search or conversion intent]

Secondary intent:
[Supporting intent]

Audience:
[Target audience]

Local or nationwide intent:
[Local, nationwide, audience-specific, or general]

Approved H1:
[Exact H1]

Approved title tag:
[Exact title tag]

Approved meta description:
[Exact meta description]

Approved direct answer:
[Exact direct answer]

Approved sections:
[Section-by-section approved copy or detailed approved outline]

Approved FAQs:
[Exact FAQ questions and answers]

Approved internal links:
[Exact destination and anchor text]

Approved CTA:
[Exact CTA label and destination]

Schema recommendation:
[Schema types and approved fields]

Notes:
[Client confirmation items or risks]
```

Claude Code should not receive a page until the page has this level of planning or an equivalent approved build prompt.

---

# 11. Page Build Prompt Requirements

Every build prompt should be specific enough that Claude Code does not need to make strategic decisions.

The prompt must specify:

```txt
Exact route
Page type
Files to create or modify
Components or templates to use
Data objects to add or update
Approved copy
Approved metadata
Approved schema text
Approved FAQs
Approved CTA labels
Approved internal links
Design instructions
Static export requirements
QA checklist
```

Avoid vague prompts like:

```txt
Build the service pages.
```

Use scoped prompts like:

```txt
Build /services/online-bookkeeping using the approved copy below. Use ServicePageTemplate, services.ts, buildServiceMetadata, buildServiceSchema, FAQ schema, BreadcrumbList schema, related services, and the Schedule a Consultation CTA. Do not alter any approved copy.
```

---

# 12. Example Service Page Handoff

## Task

```txt
Build the Online Bookkeeping service page.
```

## Route

```txt
/services/online-bookkeeping
```

## Page Type

```txt
Core service page
```

## Files to Modify

```txt
src/data/services.ts
app/services/[service]/page.tsx
src/templates/ServicePageTemplate.tsx
src/lib/metadata.ts
src/lib/schema.ts
```

## Approved Content Rule

```txt
All service page copy provided in the build prompt must be used verbatim.
```

## Claude Code May Do

```txt
Place approved content into data fields
Render the page through the service template
Add metadata using approved metadata values
Add schema using approved schema values
Add FAQ schema for visible FAQs
Add approved internal links
Ensure the route exports statically
```

## Claude Code Must Not Do

```txt
Rewrite the service description
Rewrite the H1
Rewrite the FAQ answers
Change CTA labels
Add new benefits
Add unapproved service claims
Add fake pricing
Add fake guarantees
```

---

# 13. Example Local + Service Page Handoff

## Task

```txt
Build the Tax Preparation in Atlanta, GA local + service page.
```

## Route

```txt
/service-areas/atlanta-ga/tax-preparation
```

## Page Type

```txt
Local + service page
```

## Files to Modify

```txt
src/data/locationServiceMatrix.ts
app/service-areas/[location]/[service]/page.tsx
src/templates/LocationServicePageTemplate.tsx
src/lib/metadata.ts
src/lib/schema.ts
```

## Approved Content Rule

```txt
Use all approved local copy verbatim.
```

## Claude Code May Do

```txt
Place approved city + service copy into the data object
Render the page through the local + service template
Use approved local metadata
Use approved Service schema and BreadcrumbList schema
Use LocalBusiness schema only if the prompt explicitly approves it
Add approved nearby service area links
Add approved related service links
```

## Claude Code Must Not Do

```txt
Invent local office language
Invent Atlanta-specific claims
Invent reviews
Invent business hours
Invent Google Business Profile details
Rewrite local copy
Change city wording
Change metadata wording
```

---

# 14. Example Resource Article Handoff

## Task

```txt
Build the What Is Online Bookkeeping resource article.
```

## Route

```txt
/resources/bookkeeping/what-is-online-bookkeeping
```

## Page Type

```txt
Resource article
```

## Files to Modify

```txt
src/data/resources.ts
app/resources/[category]/[slug]/page.tsx
src/templates/ResourceArticleTemplate.tsx
src/lib/metadata.ts
src/lib/schema.ts
```

## Approved Content Rule

```txt
Use the approved article copy exactly as provided.
```

## Claude Code May Do

```txt
Place approved article copy into the resource data object
Render article sections through the approved template
Add approved article metadata
Add Article schema using approved fields
Add visible FAQ section if provided
Add FAQ schema only for visible FAQs
Add approved related service CTAs
```

## Claude Code Must Not Do

```txt
Rewrite article sections
Add unapproved tax or accounting advice
Add unapproved examples
Change FAQ answers
Change CTA labels
Change article metadata
Invent an author
```

---

# 15. Content Lock for Data Files

When Claude Code places approved content into data files, the content must remain verbatim.

This applies to:

```txt
src/data/services.ts
src/data/audiences.ts
src/data/audienceServiceMatrix.ts
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
src/data/industries.ts
src/data/resources.ts
src/data/faqs.ts
src/data/metadata.ts
src/data/schema.ts
src/data/navigation.ts
src/data/ctas.ts
```

Claude Code may structure content into objects, arrays, and fields.

Claude Code must not rewrite the content while structuring it.

---

# 16. Content Lock for Metadata

Metadata must be implemented exactly as approved.

Claude Code must not change:

```txt
Title tags
Meta descriptions
Open Graph titles
Open Graph descriptions
Canonical paths
Robots directives
H1s
```

If the metadata appears too long, too short, or imperfect, Claude Code must still use it exactly unless the prompt authorizes adjustment.

If there is a technical issue, Claude Code should flag it instead of rewriting.

---

# 17. Content Lock for Schema

Schema text fields must match approved content and visible page content.

Claude Code must not rewrite:

```txt
Schema name fields
Schema description fields
FAQ schema questions
FAQ schema answers
Article headlines
Article descriptions
Service descriptions
LocalBusiness names
AreaServed labels
Breadcrumb names
```

Claude Code may build schema objects and JSON-LD rendering.

Claude Code must not add schema claims that are not in the approved prompt or visible page content.

---

# 18. Content Lock for FAQs

FAQ questions and answers are locked.

Claude Code must not:

```txt
Rewrite questions
Rewrite answers
Shorten answers
Expand answers
Reorder FAQs unless instructed
Add FAQs
Remove FAQs
Change tone
Add keywords
```

FAQ schema must only include visible FAQs.

If an FAQ is in schema but not visible, Claude Code must flag it.

---

# 19. Content Lock for CTAs

CTA labels are locked.

Claude Code must not change:

```txt
Schedule a Consultation
Request a Consultation
Speak With an Advisor
Get Started
Explore Services
View Nationwide Services
See Who We Help
Contact Hanover
```

unless the build prompt provides a different approved CTA label.

Claude Code may assign styling, layout, and button components.

Claude Code must not change the words.

---

# 20. Content Lock for Navigation

Navigation labels are locked.

Approved main navigation:

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

Claude Code must not rename navigation labels.

Do not change:

```txt
Who We Help
```

to:

```txt
Audiences
```

Do not change:

```txt
Service Areas
```

to:

```txt
Locations
```

unless an approved prompt explicitly says to do so.

---

# 21. Static Export Requirements

The site must remain compatible with Next.js static export.

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

The final build must generate:

```txt
out
```

Cloudflare Pages settings:

```txt
Build command: npm run build
Output directory: out
Production branch: main
```

---

# 22. Technical Constraints

Claude Code must not add:

```txt
API routes
Server actions
Runtime CMS dependencies
Runtime database dependencies
Runtime authentication
Middleware that must run at request time
Dynamic server rendering
Runtime image optimization
```

Unless a later approved architecture explicitly allows it.

Use static-compatible alternatives:

```txt
Local data files
Build-time route generation
Static templates
External form embeds
External form endpoints
Static assets in public/
```

---

# 23. Dynamic Route Requirements

Every dynamic route must use `generateStaticParams`.

Required dynamic routes:

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

Invalid slugs should call:

```txt
notFound()
```

---

# 24. Required Project Files to Reference

Claude Code should follow the approved documentation.

Read in this order when needed:

```txt
README.md
CLAUDE.md
docs/project-overview.md
docs/source-site-analysis.md
docs/do-not-invent.md
docs/full-build-list.md
docs/url-slug-strategy.md
docs/site-architecture.md
docs/services-data-plan.md
docs/audience-service-matrix.md
docs/location-service-matrix.md
docs/schema-plan.md
docs/metadata-plan.md
docs/content-style-guide.md
docs/folder-structure.md
docs/nextjs-static-export.md
docs/cloudflare-pages-deployment.md
docs/claude-project-instructions.md
docs/claude-code-handoff-prompt.md
docs/prelaunch-checklist.md
```

If a build prompt conflicts with the documentation, flag the conflict.

Do not rewrite the content to resolve it.

---

# 25. Site Architecture Reference

Use this approved architecture:

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

Claude Code should not create unapproved routes.

---

# 26. Approved Services Reference

## Accounting Services

```txt
online-bookkeeping
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
expense-management
budgeting-forecasting
```

## Tax Services

```txt
tax-preparation
tax-planning
tax-compliance
sales-tax-returns
year-end-tax-planning
online-tax-filing
```

## Advisory Services

```txt
cash-flow-management
outsourced-cfo-services
business-advisory-services
strategic-financial-planning
financial-performance-management
business-valuation
due-diligence-support
succession-planning
exit-strategy-planning
fundraising-investor-relations
internal-controls-review
```

Claude Code should not create new service slugs unless the build prompt explicitly approves them.

---

# 27. Approved Audience Reference

Approved audience slugs:

```txt
individuals
entrepreneurs
startups
small-businesses
medium-sized-businesses
family-owned-businesses
business-owners
growing-companies
```

Claude Code should not create new audience slugs unless the build prompt explicitly approves them.

---

# 28. Approved Service Area Reference

Approved service-area slugs:

```txt
nationwide
atlanta-ga
vinings-ga
sandy-springs-ga
marietta-ga
smyrna-ga
buckhead-atlanta-ga
alexandria-va
arlington-va
fairfax-va
richmond-va
```

Claude Code should not create new service-area slugs unless the build prompt explicitly approves them.

---

# 29. Richmond and Alexandria Accuracy Rule

The source site has a Virginia location inconsistency.

It references a Richmond, Virginia office, but the displayed address is in Alexandria, Virginia.

Claude Code must not invent or resolve this.

Until an approved build prompt confirms final language, Claude Code must treat this as unresolved.

Safe language:

```txt
Hanover serves clients in Richmond, VA through secure online accounting, tax, bookkeeping, payroll, and advisory workflows.
```

Unsafe language:

```txt
Visit Hanover's Richmond office.
```

If a prompt includes unsafe Richmond office language, Claude Code must flag it as a conflict.

---

# 30. LocalBusiness Schema Rule

Claude Code must only implement LocalBusiness or AccountingService schema with address when the build prompt explicitly approves a verified physical office.

Default rule:

```txt
Do not use LocalBusiness schema for service-area-only pages.
```

Use `Service`, `AreaServed`, `FAQPage`, and `BreadcrumbList` for service-area-only pages.

Do not invent:

```txt
Coordinates
Business hours
Address details
Department details
Office photos
Review ratings
```

---

# 31. Internal Linking Rules

Claude Code must use approved internal links and approved anchor text.

If the build prompt includes exact anchor text, use it verbatim.

Claude Code must not rewrite anchor text to improve SEO.

## Service Pages Should Link To

```txt
Parent service category
Related services
Related audiences
Nationwide + service page
Priority local + service pages
Relevant resources
Schedule consultation page
```

## Audience + Service Pages Should Link To

```txt
Parent audience page
Core service page
Related service pages
Relevant resources
Relevant FAQ page
Nationwide + service page
Schedule consultation page
```

## Local + Service Pages Should Link To

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

## Resource Pages Should Link To

```txt
Relevant service page
Relevant audience page
Relevant FAQ page
Related resources
Schedule consultation page
```

---

# 32. Forms Rule

Forms must remain static-export compatible.

Do not create internal API routes unless separately approved.

If form integration details are missing, add:

```txt
TODO: Confirm form provider, destination, spam protection, and thank-you behavior.
```

Approved static-compatible options:

```txt
External CRM form embed
External form endpoint
GHL form embed
Cloudflare Pages Functions, if approved separately
Mailto fallback, if approved
```

---

# 33. Client Portal Rule

The `/client-portal` page should only use the approved portal URL.

If the portal URL is missing, add:

```txt
TODO: Confirm final external client portal URL.
```

Do not invent portal features.

Do not describe features unless approved in the build prompt.

---

# 34. SEO Technical Files

Claude Code may create or update:

```txt
public/robots.txt
public/sitemap.xml
public/_redirects
app/sitemap/page.tsx
```

Recommended `robots.txt`:

```txt
User-agent: *
Allow: /

Sitemap: https://www.hanoveraa.com/sitemap.xml
```

Known redirects:

```txt
/accounting-services /services/accounting 301
/taxprep /services/tax-preparation 301
/aboutus /about 301
/contact-us-index /contact 301
/contact-us-form /contact 301
/our-offices /service-areas 301
```

Claude Code must not add redirects unless the build prompt approves them or they are already listed in project documentation.

---

# 35. Package Scripts

Recommended scripts:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "typecheck": "tsc --noEmit",
    "lint": "next lint"
  }
}
```

If `next lint` is not supported by the installed Next.js version, use the project's configured ESLint command.

---

# 36. Git Ignore

Ensure `.gitignore` includes:

```txt
node_modules/
.next/
out/
.env
.env.local
.env.production
.vercel/
.DS_Store
Thumbs.db
```

Do not commit:

```txt
Environment files
Build output
Node modules
Private credentials
Client secrets
```

---

# 37. Claude Code Build Report Format

After completing a build prompt, Claude Code should report:

```txt
Files created
Files modified
Routes added
Data objects added or updated
Components added or updated
Metadata added
Schema added
Internal links added
Static export status
Build status
Issues found
TODOs added
Conflicts flagged
```

Claude Code should not report that it "improved" content unless the prompt explicitly requested content editing.

---

# 38. QA Checklist for Every Handoff

Claude Code must verify:

```txt
Approved copy was used verbatim.
Metadata was used verbatim.
FAQ copy was used verbatim.
CTA labels were used verbatim.
Internal link anchor text was used verbatim.
No unapproved content was added.
No content was rewritten.
No fake claims were added.
No fake office language was added.
No em dashes were introduced in public copy.
Dynamic routes use generateStaticParams.
Invalid slugs call notFound().
Page remains static-export compatible.
Schema matches visible content.
FAQ schema only includes visible FAQs.
LocalBusiness schema is only used when explicitly approved.
Internal links point to valid routes.
Build passes.
Typecheck passes.
```

---

# 39. First Handoff Use Case

This document should be used when Claude Project has created a finished build prompt.

Example handoff command to Claude Code:

```txt
Read docs/claude-code-handoff-prompt.md first.

Then execute the approved build prompt below exactly as written.

The content in this prompt is locked. Do not rewrite, summarize, expand, shorten, improve, or copyedit the approved content.

If required content is missing, add a TODO instead of inventing copy.

If content conflicts with project rules, flag the conflict.

Build only the files and routes listed in this prompt.
```

Then paste the approved page or phase build prompt.

---

# 40. Final Claude Code Instruction

```txt
Claude Code is the implementation layer.

Claude Project owns the research, strategy, content, metadata, schema text, FAQs, and internal linking plan.

Claude Code must build the approved prompt verbatim.

Do not rewrite content.

Do not improve content.

Do not expand content.

Do not shorten content.

Do not change metadata copy.

Do not change FAQ copy.

Do not change CTA labels.

Do not change schema text fields.

Do not change internal link anchor text.

Do not invent missing content.

Do not resolve strategic conflicts silently.

If content is missing, add a TODO.

If content conflicts with project documentation, flag the conflict.

Keep the project static-export compatible for Cloudflare Pages.

Build exactly what was approved.
```
