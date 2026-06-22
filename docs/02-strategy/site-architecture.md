# Site Architecture

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the full website architecture for Hanover Accountants & Advisors.

The architecture is designed to support a nationwide-first accounting, bookkeeping, tax, payroll, outsourced CFO, and advisory website with local service-area expansion, audience-specific pages, industry pages, educational resources, FAQ pages, and conversion-focused pathways.

The site must be scalable, search-friendly, data-driven, and compatible with Next.js static export for Cloudflare Pages.

---

# 1. Architecture Summary

The new Hanover website will be structured around these primary content pillars:

```txt
Core Pages
Services
Who We Help
Service Areas
Nationwide Services
Local Service Areas
Industries
Resources
FAQs
Conversion Pages
```

The architecture should help users and search engines understand:

```txt
What Hanover offers
Who Hanover helps
Where Hanover provides services
How Hanover delivers services online nationwide
Which industries Hanover supports
What questions Hanover answers
How a visitor can become a lead
```

---

# 2. Primary Site Structure

The recommended structure is:

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

# 3. Core Pages

Core pages support general brand, trust, contact, conversion, legal, and user navigation needs.

```txt
/
/about
/contact
/schedule-consultation
/get-started
/client-portal
/privacy-policy
/terms-of-use
/sitemap
```

## Core Page Roles

| Page                  | URL                      | Purpose                                                                                                 |
| --------------------- | ------------------------ | ------------------------------------------------------------------------------------------------------- |
| Home                  | `/`                      | Primary entry page, nationwide positioning, services, audiences, service areas, trust, and CTA          |
| About                 | `/about`                 | Company story, service philosophy, secure technology, professional support, office/service-area context |
| Contact               | `/contact`               | General inquiry page, office/contact details, consultation pathway                                      |
| Schedule Consultation | `/schedule-consultation` | Primary lead-generation page                                                                            |
| Get Started           | `/get-started`           | New client onboarding pathway                                                                           |
| Client Portal         | `/client-portal`         | Existing client access point                                                                            |
| Privacy Policy        | `/privacy-policy`        | Legal/privacy content                                                                                   |
| Terms of Use          | `/terms-of-use`          | Legal terms                                                                                             |
| Sitemap               | `/sitemap`               | Human-readable HTML sitemap                                                                             |

---

# 4. Services Architecture

The services section is the main commercial authority pillar.

## Services Hub

```txt
/services
```

The services hub should introduce all Hanover service categories and link to service category hubs and individual service pages.

## Service Category Hubs

```txt
/services/accounting
/services/tax
/services/advisory
```

## Service Category Roles

| Hub                 | URL                    | Purpose                                                                                                                                                                                  |
| ------------------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Accounting Services | `/services/accounting` | Groups bookkeeping, monthly accounting, client accounting, reporting, payroll, expenses, budgeting, and forecasting                                                                      |
| Tax Services        | `/services/tax`        | Groups tax preparation, tax planning, tax compliance, sales tax returns, year-end planning, and online filing                                                                            |
| Advisory Services   | `/services/advisory`   | Groups cash flow, outsourced CFO, business advisory, strategic planning, performance management, valuation, due diligence, succession, exit planning, fundraising, and internal controls |

---

# 5. Individual Service Pages

Individual service pages explain each core service at a national level.

## Accounting Service Pages

```txt
/services/online-bookkeeping
/services/monthly-accounting-services
/services/client-accounting-services
/services/financial-reporting
/services/payroll-services
/services/expense-management
/services/budgeting-forecasting
```

## Tax Service Pages

```txt
/services/tax-preparation
/services/tax-planning
/services/tax-compliance
/services/sales-tax-returns
/services/year-end-tax-planning
/services/online-tax-filing
```

## Advisory Service Pages

```txt
/services/cash-flow-management
/services/outsourced-cfo-services
/services/business-advisory-services
/services/strategic-financial-planning
/services/financial-performance-management
/services/business-valuation
/services/due-diligence-support
/services/succession-planning
/services/exit-strategy-planning
/services/fundraising-investor-relations
/services/internal-controls-review
```

## Service Page Role

Each service page should answer:

```txt
What is the service?
Who is it for?
What does Hanover provide?
How does the online workflow work?
What problems does the service help solve?
What related services should users consider?
What is the next step?
```

---

# 6. Who We Help Architecture

The audience section supports customer-specific intent and conversion.

## Audience Hub

```txt
/who-we-help
```

The audience hub should organize Hanover's services by client type.

## Audience Pages

```txt
/who-we-help/individuals
/who-we-help/entrepreneurs
/who-we-help/startups
/who-we-help/small-businesses
/who-we-help/medium-sized-businesses
/who-we-help/family-owned-businesses
/who-we-help/business-owners
/who-we-help/growing-companies
```

## Audience Page Role

Each audience page should answer:

```txt
Does Hanover work with this type of client?
What challenges does this audience usually face?
Which services are most relevant?
How does Hanover support them online?
What should the visitor do next?
```

---

# 7. Audience + Service Architecture

Audience + service pages target high-intent searches where a user is looking for a specific service for a specific type of client.

## Slug Pattern

```txt
/who-we-help/[audience]/[service]
```

## Examples

```txt
/who-we-help/startups/online-bookkeeping
/who-we-help/small-businesses/tax-preparation
/who-we-help/family-owned-businesses/outsourced-cfo-services
/who-we-help/business-owners/tax-planning
/who-we-help/growing-companies/payroll-services
```

## Audience + Service Page Role

Each page should answer:

```txt
How does this service apply to this audience?
Why does this audience need this service?
What does Hanover provide?
What are the common problems solved?
How does the nationwide online workflow work?
Which related services are useful?
How can the visitor schedule a consultation?
```

## Architecture Note

Audience + service pages must be unique and useful.

Do not create pages that only swap the audience name.

---

# 8. Service Areas Architecture

The service-area section is used instead of a simple locations section because Hanover is positioned as nationwide-first with local service-area support.

## Service Areas Hub

```txt
/service-areas
```

The service areas hub should explain:

```txt
Hanover serves clients nationwide.
Hanover supports local service-area visibility in Georgia and Virginia markets.
Some markets may be physical office locations.
Other markets may be served through secure online workflows.
```

---

# 9. Nationwide Service Area Architecture

## Nationwide Service Area Page

```txt
/service-areas/nationwide
```

This page should establish national service availability.

## Nationwide + Service Pages

```txt
/service-areas/nationwide/[service]
```

Examples:

```txt
/service-areas/nationwide/online-bookkeeping
/service-areas/nationwide/tax-preparation
/service-areas/nationwide/payroll-services
/service-areas/nationwide/outsourced-cfo-services
```

## Nationwide Page Role

Nationwide pages should answer:

```txt
Can Hanover provide this service nationwide?
How does online service delivery work?
How do clients share documents securely?
Who is this service for?
What services are available nationwide?
How does a visitor schedule a consultation?
```

---

# 10. Local Service Area Architecture

Local service-area pages support local search, service-area clarity, Google Business Profile alignment, Apple Business Connect alignment, and local conversion.

## Local Service Area Pages

```txt
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

## Local Page Role

Each local page should answer:

```txt
Does Hanover serve this area?
Is this a physical office or service area?
Which services are available in this area?
Who does Hanover help in this area?
How does the online workflow work for local clients?
What nearby markets are served?
How can the visitor schedule a consultation?
```

## Local Accuracy Rule

Do not claim a physical office unless verified.

Use service-area language for nearby or remote markets.

---

# 11. Local + Service Architecture

Local + service pages target high-intent local searches.

## Slug Pattern

```txt
/service-areas/[location]/[service]
```

## Examples

```txt
/service-areas/atlanta-ga/tax-preparation
/service-areas/atlanta-ga/online-bookkeeping
/service-areas/marietta-ga/payroll-services
/service-areas/alexandria-va/business-advisory-services
/service-areas/arlington-va/outsourced-cfo-services
/service-areas/fairfax-va/cash-flow-management
```

## Local + Service Page Role

Each local + service page should answer:

```txt
Does Hanover provide this service in this local market?
How does the service work for clients in this area?
Is the service delivered online, locally, or both?
What is included?
Who is this service for?
What related local services are available?
What is the next step?
```

## Local + Service Content Rule

Every local + service page must be individually written.

Do not create thin duplicate pages.

Do not create city-name swap pages.

---

# 12. Industries Architecture

The industry section supports topical authority and business relevance.

## Industries Hub

```txt
/industries
```

## Core Industry Pages

```txt
/industries/agriculture
/industries/construction
/industries/design-firms
/industries/food-processing
/industries/professional-services
/industries/textile-businesses
```

## Optional Industry + Service Pages

```txt
/industries/[industry]/[service]
```

Examples:

```txt
/industries/construction/payroll-services
/industries/professional-services/outsourced-cfo-services
/industries/food-processing/tax-compliance
```

## Industry Page Role

Each industry page should answer:

```txt
What accounting, tax, payroll, reporting, or advisory challenges are common in this industry?
Which Hanover services are relevant?
How does Hanover support businesses in this industry?
How does the online workflow work?
What resources or FAQs are related?
How can the visitor schedule a consultation?
```

---

# 13. Resources Architecture

The resources section supports informational SEO, AEO, People Also Ask, featured snippets, LLM search, and topical authority.

## Resource Hub

```txt
/resources
```

## Resource Category Pages

```txt
/resources/bookkeeping
/resources/tax-preparation
/resources/tax-planning
/resources/business-accounting
/resources/payroll
/resources/cfo-advisory
/resources/small-business-finance
/resources/financial-reporting
/resources/cash-flow
/resources/business-advisory
/resources/industry-guides
```

## Resource Article Pattern

```txt
/resources/[category]/[slug]
```

## Resource Article Examples

```txt
/resources/bookkeeping/what-is-online-bookkeeping
/resources/tax-preparation/online-tax-preparation-checklist
/resources/tax-planning/year-end-tax-planning-checklist
/resources/payroll/payroll-tax-filing-guide
/resources/cfo-advisory/when-to-hire-an-outsourced-cfo
/resources/business-advisory/succession-planning-for-family-businesses
```

## Resource Page Role

Resource pages should answer informational questions and then link users toward relevant services.

Each article should include:

```txt
Plain-English explanation
Helpful educational content
Related service links
Related audience links
FAQ section
Consultation CTA
Article schema
FAQ schema where appropriate
```

---

# 14. FAQ Architecture

FAQ pages support AEO, People Also Ask, featured snippets, rich snippets, and LLM answer extraction.

## FAQ Hub

```txt
/faqs
```

## FAQ Category Pages

```txt
/faqs/online-bookkeeping
/faqs/tax-preparation
/faqs/monthly-accounting
/faqs/payroll-services
/faqs/outsourced-cfo
/faqs/business-advisory
/faqs/secure-client-portal
/faqs/nationwide-services
/faqs/service-areas
```

## FAQ Page Role

FAQ pages should:

```txt
Answer common questions clearly
Use concise direct answers
Link to relevant services
Link to relevant resources
Support schema markup
Improve user trust
Create conversion pathways
```

---

# 15. Conversion Architecture

Conversion pages and sections should be built into the site architecture from the beginning.

## Conversion Pages

```txt
/contact
/schedule-consultation
/get-started
/client-portal
```

## Primary CTA Destination

```txt
/schedule-consultation
```

## Secondary CTA Destinations

```txt
/services
/service-areas/nationwide
/who-we-help
/contact
/get-started
```

## CTA Placement

Every major page should include:

```txt
Primary CTA near the top
Contextual CTA in the body
Final CTA near the bottom
```

---

# 16. Navigation Architecture

## Main Navigation

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

## Services Dropdown

```txt
Accounting Services
Tax Services
Advisory Services
Online Bookkeeping
Monthly Accounting Services
Tax Preparation
Tax Planning
Payroll Services
Outsourced CFO Services
Business Advisory Services
```

## Who We Help Dropdown

```txt
Individuals
Entrepreneurs
Startups
Small Businesses
Medium-Sized Businesses
Family-Owned Businesses
Business Owners
Growing Companies
```

## Nationwide Services Dropdown

```txt
Nationwide Accounting Services
Nationwide Online Bookkeeping
Nationwide Tax Preparation
Nationwide Payroll Services
Nationwide Outsourced CFO Services
Nationwide Business Advisory Services
```

## Service Areas Dropdown

```txt
Nationwide
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

## Industries Dropdown

```txt
Agriculture
Construction
Design Firms
Food Processing
Professional Services
Textile Businesses
```

## Navigation Rule

Do not place every local + service page or audience + service page in the main navigation.

Use hub pages, related links, footers, HTML sitemap, XML sitemap, and contextual sections for discovery.

---

# 17. Footer Architecture

The footer should include:

```txt
Brand summary
Primary CTA
Contact information
Client portal link
Services links
Who We Help links
Nationwide Services links
Priority Service Areas links
Industries links
Resources links
Legal links
Social links, if approved
```

## Footer Service Links

Include priority services only:

```txt
Online Bookkeeping
Monthly Accounting Services
Tax Preparation
Tax Planning
Payroll Services
Outsourced CFO Services
Business Advisory Services
```

## Footer Service Area Links

Include priority service areas only:

```txt
Nationwide
Atlanta, GA
Alexandria, VA
Richmond, VA, if approved
```

---

# 18. Internal Linking Architecture

Internal linking should connect each content layer.

## Service Pages Should Link To

```txt
Service category hub
Related service pages
Related audience pages
Nationwide + service page
Priority local + service pages
Relevant resource articles
Consultation page
```

## Audience Pages Should Link To

```txt
Audience + service pages
Core service pages
Relevant resources
Service areas hub
Consultation page
```

## Audience + Service Pages Should Link To

```txt
Parent audience page
Core service page
Related audience + service pages
Related resources
Consultation page
```

## Nationwide Pages Should Link To

```txt
Core service page
Related nationwide + service pages
Audience pages
Priority service areas
Consultation page
```

## Local Pages Should Link To

```txt
Local + service pages
Nearby service-area pages
Nationwide hub
Core services
Consultation page
```

## Local + Service Pages Should Link To

```txt
Parent local service-area page
Core service page
Nationwide + service page
Related local service pages
Nearby service areas
Consultation page
```

## Resource Pages Should Link To

```txt
Relevant service page
Relevant audience page
Relevant FAQ page
Related resources
Consultation page
```

---

# 19. Breadcrumb Architecture

Breadcrumbs should appear on all pages except the homepage.

## Examples

Service page:

```txt
Home > Services > Online Bookkeeping
```

Audience + service page:

```txt
Home > Who We Help > Startups > Online Bookkeeping
```

Nationwide + service page:

```txt
Home > Service Areas > Nationwide > Online Bookkeeping
```

Local + service page:

```txt
Home > Service Areas > Atlanta, GA > Tax Preparation
```

Resource article:

```txt
Home > Resources > Tax Planning > Year-End Tax Planning Checklist
```

---

# 20. Schema Architecture

The architecture should support schema at every page type.

## Global Schema

```txt
Organization
AccountingService
ProfessionalService
WebSite
SiteNavigationElement
BreadcrumbList
```

## Service Pages

```txt
Service
FAQPage
BreadcrumbList
```

## Nationwide Pages

```txt
Service
Organization
AreaServed: United States
FAQPage
BreadcrumbList
```

## Local Physical Office Pages

Use only if verified:

```txt
LocalBusiness
ProfessionalService
PostalAddress
OpeningHoursSpecification
BreadcrumbList
```

## Service Area Pages Without Physical Offices

```txt
Service
AreaServed
FAQPage
BreadcrumbList
```

## Resource Pages

```txt
Article
BlogPosting
FAQPage, where relevant
BreadcrumbList
```

## FAQ Pages

```txt
FAQPage
BreadcrumbList
```

---

# 21. Metadata Architecture

Every route should have:

```txt
Unique title tag
Unique meta description
Single H1
Canonical URL
Open Graph title
Open Graph description
Clean slug
Relevant internal links
```

Do not duplicate metadata across matrix pages.

Do not canonical unique matrix pages back to the broad service page.

---

# 22. Next.js App Router Architecture

Recommended folder structure:

```txt
app/
  page.tsx
  about/
    page.tsx
  contact/
    page.tsx
  schedule-consultation/
    page.tsx
  get-started/
    page.tsx
  client-portal/
    page.tsx

  services/
    page.tsx
    accounting/
      page.tsx
    tax/
      page.tsx
    advisory/
      page.tsx
    [service]/
      page.tsx

  who-we-help/
    page.tsx
    [audience]/
      page.tsx
      [service]/
        page.tsx

  service-areas/
    page.tsx
    nationwide/
      page.tsx
      [service]/
        page.tsx
    [location]/
      page.tsx
      [service]/
        page.tsx

  industries/
    page.tsx
    [industry]/
      page.tsx
      [service]/
        page.tsx

  resources/
    page.tsx
    [category]/
      page.tsx
      [slug]/
        page.tsx

  faqs/
    page.tsx
    [category]/
      page.tsx

  sitemap/
    page.tsx
  not-found.tsx
```

---

# 23. Data Layer Architecture

The site should use centralized data files.

```txt
src/data/site.ts
src/data/navigation.ts
src/data/services.ts
src/data/serviceCategories.ts
src/data/audiences.ts
src/data/audienceServiceMatrix.ts
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
src/data/industries.ts
src/data/resources.ts
src/data/faqs.ts
src/data/schema.ts
src/data/ctas.ts
```

## Data Layer Purpose

The data layer should control:

```txt
Slugs
Titles
Descriptions
Page paths
Category relationships
Related pages
Matrix generation
Navigation links
Metadata defaults
Schema inputs
CTA labels
```

---

# 24. Component Architecture

Recommended reusable components:

```txt
src/components/layout/Header.tsx
src/components/layout/Footer.tsx
src/components/layout/MobileNav.tsx
src/components/layout/Breadcrumbs.tsx

src/components/sections/Hero.tsx
src/components/sections/DirectAnswer.tsx
src/components/sections/ServiceGrid.tsx
src/components/sections/AudienceGrid.tsx
src/components/sections/ServiceAreaGrid.tsx
src/components/sections/IndustryGrid.tsx
src/components/sections/FAQSection.tsx
src/components/sections/CTASection.tsx
src/components/sections/RelatedLinks.tsx
src/components/sections/ProcessSection.tsx
src/components/sections/TrustSection.tsx

src/components/cards/ServiceCard.tsx
src/components/cards/AudienceCard.tsx
src/components/cards/LocationCard.tsx
src/components/cards/IndustryCard.tsx
src/components/cards/ResourceCard.tsx

src/components/schema/JsonLd.tsx
```

---

# 25. Static Export Architecture

The site must remain compatible with Cloudflare Pages static export.

Required build model:

```txt
Next.js App Router
TypeScript
Static export
Trailing slash support
Unoptimized images
No required server runtime
No server-only API dependencies
```

Required `next.config.ts` direction:

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

Cloudflare output directory:

```txt
out
```

---

# 26. Sitemap Architecture

The project should generate or maintain:

```txt
/sitemap.xml
/sitemap
```

## XML Sitemap Should Include

```txt
Core pages
Service pages
Audience pages
Audience + service pages
Service-area pages
Nationwide + service pages
Local + service pages
Industry pages
Resource pages
FAQ pages
```

## HTML Sitemap Should Include

A user-friendly sitemap grouped by:

```txt
Core Pages
Services
Who We Help
Nationwide Services
Service Areas
Industries
Resources
FAQs
```

---

# 27. Redirect Architecture

Known old URLs should redirect to the new structure.

```txt
/accounting-services  -> /services/accounting
/taxprep              -> /services/tax-preparation
/aboutus              -> /about
/contact-us-index     -> /contact
/contact-us-form      -> /contact
/our-offices          -> /service-areas
```

If needed, use a Cloudflare Pages `_redirects` file:

```txt
/accounting-services /services/accounting 301
/taxprep /services/tax-preparation 301
/aboutus /about 301
/contact-us-index /contact 301
/contact-us-form /contact 301
/our-offices /service-areas 301
```

---

# 28. Architecture Quality Rules

The architecture must avoid:

```txt
Thin local pages
Duplicate city-name swap pages
Fake office claims
Fake reviews
Fake credentials
Unsupported pricing
Unsupported guarantees
Duplicate metadata
Broken internal links
Confusing navigation
Unclear conversion paths
Index bloat from low-quality pages
```

The architecture must support:

```txt
Nationwide positioning
Local service-area visibility
Unique page content
Strong internal links
Structured data
Search-friendly routing
Conversion paths
Static export compatibility
Long-term content expansion
```

---

# 29. Final Architecture Summary

The final Hanover site architecture is:

```txt
/services/[service]
/who-we-help/[audience]
/who-we-help/[audience]/[service]
/service-areas/nationwide
/service-areas/nationwide/[service]
/service-areas/[city-state]
/service-areas/[city-state]/[service]
/industries/[industry]
/resources/[category]/[slug]
/faqs/[category]
```

This architecture allows Hanover to build national authority, local service-area visibility, audience-specific conversion pathways, industry relevance, resource-based topical authority, AEO coverage, GEO coverage, LLM visibility, and a scalable Next.js static website ready for Cloudflare Pages.
