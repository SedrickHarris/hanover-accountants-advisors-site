# URL Slug Strategy

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the URL structure, slug rules, hierarchy, and routing strategy for the Hanover Accountants & Advisors website rebuild.

The new site will be built as a nationwide-first online accounting, bookkeeping, tax, payroll, outsourced CFO, and advisory website with strong local service-area support.

The URL structure must support:

* SEO
* GEO
* AEO
* Nationwide service intent
* Local service-area intent
* Audience-specific search intent
* LLM search visibility
* Featured snippets
* People Also Ask
* Rich snippets
* Google Search Console
* Bing Webmaster
* Apple Search
* Google Business Profile support
* Customer engagement
* Customer conversion

---

# 1. Core Slug Philosophy

The site should use a clean, scalable, human-readable URL structure.

Every URL should communicate:

```txt
What the page is about
Who the page is for
Where the service is available, when relevant
How the page relates to the larger site architecture
```

The structure should be easy for users, search engines, and LLM systems to understand.

## Core URL Model

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

---

# 2. General URL Rules

Use these rules across the entire site.

```txt
Use lowercase letters only.
Use hyphens between words.
Do not use underscores.
Do not use spaces.
Do not use special characters.
Do not use dates in service or hub URLs.
Do not use vague slugs where a specific slug is better.
Do not use excessively long URLs.
Use plural nouns where the common search term is plural.
Use singular nouns where the service is normally searched in singular.
Use city-state format for local service-area pages.
Use consistent service slugs across all matrices.
Use trailing slashes if required by the final Next.js static export configuration.
```

## Examples

Good:

```txt
/services/online-bookkeeping
/who-we-help/small-businesses/tax-preparation
/service-areas/atlanta-ga/payroll-services
/resources/tax-planning/year-end-tax-planning-checklist
```

Avoid:

```txt
/Services/Online_Bookkeeping
/service-pages/bookkeeping-for-small-businesses-in-atlanta-georgia-usa
/location/atlanta
/blog/2026/06/22/tax-tips
/solutions
```

---

# 3. Top-Level Core Pages

These are primary site pages.

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

## Notes

* `/` is the homepage.
* `/about` replaces the legacy `/aboutus`.
* `/contact` replaces legacy contact URLs.
* `/client-portal` should point users to the external secure client portal.
* `/sitemap` is the human-readable HTML sitemap.
* `/privacy-policy` and `/terms-of-use` should remain clean legal URLs.

---

# 4. Service URL Strategy

## Service Hub

```txt
/services
```

The `/services` page is the main service hub.

It should link to:

```txt
/services/accounting
/services/tax
/services/advisory
/services/[service]
```

## Service Category Hubs

```txt
/services/accounting
/services/tax
/services/advisory
```

## Service Category Purpose

| URL                    | Purpose                                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------ |
| `/services/accounting` | Groups bookkeeping, accounting, payroll, reporting, expense, budgeting, and forecasting services |
| `/services/tax`        | Groups tax preparation, tax planning, tax compliance, sales tax, and online tax filing           |
| `/services/advisory`   | Groups CFO, business advisory, cash flow, valuation, succession, and investor support services   |

---

# 5. Core Service Slugs

Use these exact slugs consistently across service pages, audience + service pages, nationwide + service pages, and local + service pages.

## Accounting Service Slugs

```txt
online-bookkeeping
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
expense-management
budgeting-forecasting
```

## Accounting Service URLs

```txt
/services/online-bookkeeping
/services/monthly-accounting-services
/services/client-accounting-services
/services/financial-reporting
/services/payroll-services
/services/expense-management
/services/budgeting-forecasting
```

## Tax Service Slugs

```txt
tax-preparation
tax-planning
tax-compliance
sales-tax-returns
year-end-tax-planning
online-tax-filing
```

## Tax Service URLs

```txt
/services/tax-preparation
/services/tax-planning
/services/tax-compliance
/services/sales-tax-returns
/services/year-end-tax-planning
/services/online-tax-filing
```

## Advisory Service Slugs

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

## Advisory Service URLs

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

---

# 6. Audience URL Strategy

## Audience Hub

```txt
/who-we-help
```

The `/who-we-help` page is the main audience hub.

It should link to all audience pages and priority audience + service pages.

## Audience Slugs

Use these exact audience slugs:

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

## Audience URLs

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

## Audience + Service Slug Pattern

Use this pattern:

```txt
/who-we-help/[audience]/[service]
```

Examples:

```txt
/who-we-help/startups/online-bookkeeping
/who-we-help/small-businesses/tax-preparation
/who-we-help/family-owned-businesses/outsourced-cfo-services
/who-we-help/business-owners/tax-planning
```

## Why This Pattern Works

This structure keeps audience-specific pages organized under the audience hub.

It clearly tells search engines and users:

```txt
This is a service page for a specific audience.
```

This is better than creating flat URLs like:

```txt
/bookkeeping-for-startups
/tax-preparation-for-small-businesses
```

The nested structure is easier to scale and maintain in a data-driven Next.js build.

---

# 7. Service Area URL Strategy

Use `/service-areas`, not only `/locations`.

Hanover is being positioned as a nationwide online service provider with local service-area support.

## Service Areas Hub

```txt
/service-areas
```

## Nationwide Service-Area Hub

```txt
/service-areas/nationwide
```

## Local Service-Area Pattern

```txt
/service-areas/[city-state]
```

## Local + Service Pattern

```txt
/service-areas/[city-state]/[service]
```

---

# 8. Nationwide Service URL Strategy

Nationwide pages target national, online, virtual, and remote intent.

## Nationwide Hub

```txt
/service-areas/nationwide
```

## Nationwide + Service Pattern

```txt
/service-areas/nationwide/[service]
```

## Nationwide + Service Examples

```txt
/service-areas/nationwide/online-bookkeeping
/service-areas/nationwide/tax-preparation
/service-areas/nationwide/payroll-services
/service-areas/nationwide/outsourced-cfo-services
/service-areas/nationwide/business-advisory-services
```

## Nationwide Page Purpose

Nationwide + service pages should answer:

```txt
Does Hanover provide this service nationwide?
How does the online service process work?
Who is this service for?
How does secure document sharing work?
What does Hanover provide?
What is the next step?
```

---

# 9. Local Service-Area Slugs

Use city plus state abbreviation for local slugs.

## Georgia Service-Area Slugs

```txt
atlanta-ga
vinings-ga
sandy-springs-ga
marietta-ga
smyrna-ga
buckhead-atlanta-ga
```

## Virginia Service-Area Slugs

```txt
alexandria-va
arlington-va
fairfax-va
richmond-va
```

## Local Service-Area URLs

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

## Local + Service Examples

```txt
/service-areas/atlanta-ga/tax-preparation
/service-areas/atlanta-ga/online-bookkeeping
/service-areas/sandy-springs-ga/payroll-services
/service-areas/marietta-ga/outsourced-cfo-services
/service-areas/alexandria-va/tax-compliance
/service-areas/arlington-va/business-advisory-services
/service-areas/fairfax-va/cash-flow-management
/service-areas/richmond-va/monthly-accounting-services
```

---

# 10. Local Slug Accuracy Rules

Do not create fake office URLs.

A local service-area URL does not automatically mean Hanover has a physical office there.

## Physical Office Pages

Use physical office language only if verified.

Example:

```txt
/service-areas/atlanta-ga
```

May include office language if the Atlanta office is verified.

## Service Area Pages

Use service-area language for markets without a verified physical office.

Example:

```txt
/service-areas/sandy-springs-ga
```

Should use language such as:

```txt
Hanover serves clients in Sandy Springs through secure online accounting, tax, bookkeeping, payroll, and advisory services.
```

Do not write:

```txt
Visit our Sandy Springs office.
```

Unless a Sandy Springs office is confirmed.

---

# 11. Industry URL Strategy

## Industry Hub

```txt
/industries
```

## Industry Slugs

```txt
agriculture
construction
design-firms
food-processing
professional-services
textile-businesses
```

## Industry URLs

```txt
/industries/agriculture
/industries/construction
/industries/design-firms
/industries/food-processing
/industries/professional-services
/industries/textile-businesses
```

## Optional Industry + Service Pattern

Use only when the content can be uniquely written and useful.

```txt
/industries/[industry]/[service]
```

Examples:

```txt
/industries/construction/payroll-services
/industries/professional-services/outsourced-cfo-services
/industries/food-processing/tax-compliance
```

---

# 12. Resource URL Strategy

## Resource Hub

```txt
/resources
```

## Resource Category Pattern

```txt
/resources/[category]
```

## Resource Article Pattern

```txt
/resources/[category]/[slug]
```

## Resource Category Slugs

```txt
bookkeeping
tax-preparation
tax-planning
business-accounting
payroll
cfo-advisory
small-business-finance
financial-reporting
cash-flow
business-advisory
industry-guides
```

## Resource Category URLs

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

## Resource Article Examples

```txt
/resources/bookkeeping/what-is-online-bookkeeping
/resources/bookkeeping/monthly-bookkeeping-checklist
/resources/tax-preparation/online-tax-preparation-checklist
/resources/tax-planning/year-end-tax-planning-checklist
/resources/payroll/payroll-tax-filing-guide
/resources/cfo-advisory/when-to-hire-an-outsourced-cfo
/resources/cash-flow/how-to-create-a-cash-flow-forecast
/resources/business-advisory/succession-planning-for-family-businesses
/resources/industry-guides/accounting-for-construction-businesses
```

## Blog URL Note

Do not use `/blog` unless the client specifically wants that label.

Use `/resources` because it sounds more professional and supports educational content, guides, FAQs, and topical authority.

---

# 13. FAQ URL Strategy

## FAQ Hub

```txt
/faqs
```

## FAQ Category Pattern

```txt
/faqs/[category]
```

## FAQ Category URLs

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

## FAQ Page Purpose

FAQ pages should support:

```txt
AEO
People Also Ask
Featured snippets
Rich snippets
LLM answer extraction
Internal linking
User trust
Conversion
```

---

# 14. Conversion URL Strategy

Use simple, action-oriented URLs.

```txt
/contact
/schedule-consultation
/get-started
/client-portal
```

## Conversion Page Roles

| URL                      | Role                                          |
| ------------------------ | --------------------------------------------- |
| `/contact`               | General contact, office info, inquiry routing |
| `/schedule-consultation` | Main consultation request page                |
| `/get-started`           | New client onboarding path                    |
| `/client-portal`         | Existing client portal entry point            |

## CTA Link Rules

Primary CTA buttons should usually point to:

```txt
/schedule-consultation
```

Secondary CTA buttons can point to:

```txt
/services
/service-areas/nationwide
/who-we-help
/contact
```

---

# 15. Legal URL Strategy

Keep legal URLs simple.

```txt
/privacy-policy
/terms-of-use
```

Do not put legal pages under `/legal` unless the old site already has that structure and there is a strategic reason to preserve it.

---

# 16. Sitemap URL Strategy

Use both an XML sitemap and a human-readable HTML sitemap.

## XML Sitemap

```txt
/sitemap.xml
```

## HTML Sitemap

```txt
/sitemap
```

The HTML sitemap should include:

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
Conversion pages
```

---

# 17. Redirect Strategy

Redirect old URLs into the new structure.

## Known Legacy Redirects

```txt
/accounting-services  -> /services/accounting
/taxprep              -> /services/tax-preparation
/aboutus              -> /about
/contact-us-index     -> /contact
/contact-us-form      -> /contact
/our-offices          -> /service-areas
```

## Redirect Rules

Use 301 redirects for permanent old-to-new URL mapping.

If Cloudflare Pages static export does not support server-side redirects directly through Next.js, configure redirects using Cloudflare Pages redirect rules or a `_redirects` file if applicable.

## Redirect File Pattern

Potential `_redirects` file:

```txt
/accounting-services /services/accounting 301
/taxprep /services/tax-preparation 301
/aboutus /about 301
/contact-us-index /contact 301
/contact-us-form /contact 301
/our-offices /service-areas 301
```

---

# 18. Canonical URL Strategy

Each page should self-canonicalize unless there is a specific reason not to.

## Examples

```txt
/services/tax-preparation
```

Canonical:

```txt
https://www.hanoveraa.com/services/tax-preparation/
```

```txt
/service-areas/atlanta-ga/tax-preparation
```

Canonical:

```txt
https://www.hanoveraa.com/service-areas/atlanta-ga/tax-preparation/
```

## Matrix Page Canonicals

Do not canonical matrix pages to the broad service page if the matrix pages are unique and useful.

For example, do not canonical:

```txt
/service-areas/atlanta-ga/tax-preparation
```

to:

```txt
/services/tax-preparation
```

If the local page has unique local content, it should self-canonicalize.

---

# 19. URL Indexing Strategy

Most useful, complete pages should be indexable.

Index:

```txt
Core pages
Service pages
Audience pages
Audience + service pages
Nationwide service pages
Local service-area pages
Local + service pages
Industry pages
Resource pages
FAQ pages
```

Noindex only if needed for:

```txt
Temporary drafts
Duplicate utility pages
Internal-only test pages
Thank-you pages, if used
Search result pages, if any
Filtered pages, if any
```

Do not noindex local pages just because they are matrix pages if they are individually written and useful.

---

# 20. Route Grouping for Next.js

Recommended App Router structure:

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
```

---

# 21. Slug Data File Strategy

Use centralized data files so slugs remain consistent.

Recommended files:

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
```

Each service should have one official slug.

Example service object:

```ts
{
  title: "Online Bookkeeping",
  slug: "online-bookkeeping",
  category: "accounting",
  path: "/services/online-bookkeeping",
}
```

Each service-area page should use one official slug.

Example location object:

```ts
{
  title: "Atlanta, GA",
  slug: "atlanta-ga",
  type: "office-or-primary-market",
  path: "/service-areas/atlanta-ga",
}
```

---

# 22. Internal Linking Slug Rules

Use consistent URL paths in all internal links.

## Service Page Links

Service pages should link to:

```txt
/services/[related-service]
/services/[category]
/who-we-help/[audience]
/service-areas/nationwide/[service]
/service-areas/[priority-location]/[service]
/resources/[category]/[article]
/schedule-consultation
```

## Audience Page Links

Audience pages should link to:

```txt
/who-we-help/[audience]/[service]
/services/[service]
/resources/[category]/[article]
/schedule-consultation
```

## Location Page Links

Location pages should link to:

```txt
/service-areas/[location]/[service]
/service-areas/nationwide
/service-areas/[nearby-location]
/services/[service]
/schedule-consultation
```

## Resource Page Links

Resource pages should link to:

```txt
/services/[service]
/who-we-help/[audience]
/service-areas/nationwide/[service]
/resources/[related-category]/[related-article]
/schedule-consultation
```

---

# 23. URL Naming Decisions

## Use `/service-areas`, not `/locations`

Reason:

```txt
Hanover is being positioned as nationwide-first.
The company can serve clients through online workflows.
Local markets may include physical offices, nearby markets, and remote service areas.
Service-area language avoids fake office implications.
```

## Use `/who-we-help`, not `/audiences`

Reason:

```txt
It is more customer-friendly.
It supports conversion.
It is easier for users to understand.
```

## Use `/resources`, not `/blog`

Reason:

```txt
Resources sounds more professional for accounting, tax, and advisory content.
It can include guides, FAQs, checklists, articles, and educational content.
```

## Use `/services/advisory`, not `/services/financial-advisory`

Reason:

```txt
Advisory is broader and can house outsourced CFO, business advisory, cash flow, valuation, succession, and investor support services.
```

---

# 24. URL Conflict Rules

Avoid duplicate or overlapping URLs.

Do not create both:

```txt
/services/bookkeeping
/services/online-bookkeeping
```

Use:

```txt
/services/online-bookkeeping
```

Do not create both:

```txt
/service-areas/atlanta
/service-areas/atlanta-ga
```

Use:

```txt
/service-areas/atlanta-ga
```

Do not create both:

```txt
/who-we-help/small-business
/who-we-help/small-businesses
```

Use:

```txt
/who-we-help/small-businesses
```

---

# 25. Recommended URL Priority for Launch

## Phase 1 Priority URLs

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
/services/online-bookkeeping
/services/monthly-accounting-services
/services/client-accounting-services
/services/financial-reporting
/services/payroll-services
/services/tax-preparation
/services/tax-planning
/services/tax-compliance
/services/outsourced-cfo-services
/services/business-advisory-services
/services/cash-flow-management
/who-we-help
/service-areas
/service-areas/nationwide
/industries
/resources
/faqs
```

## Phase 2 Priority URLs

```txt
/service-areas/nationwide/online-bookkeeping
/service-areas/nationwide/monthly-accounting-services
/service-areas/nationwide/client-accounting-services
/service-areas/nationwide/financial-reporting
/service-areas/nationwide/payroll-services
/service-areas/nationwide/tax-preparation
/service-areas/nationwide/tax-planning
/service-areas/nationwide/tax-compliance
/service-areas/nationwide/sales-tax-returns
/service-areas/nationwide/cash-flow-management
/service-areas/nationwide/outsourced-cfo-services
/service-areas/nationwide/business-advisory-services
```

## Phase 3 Priority URLs

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

Then build the full audience + service matrix.

## Phase 4 Priority URLs

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

Then build the full local + service matrix.

---

# 26. Final URL Strategy

The final Hanover URL architecture should be:

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

This structure gives Hanover a clean, scalable website architecture for nationwide accounting services, local service-area visibility, audience-specific conversion, industry authority, educational resources, structured data, AEO, GEO, LLM search, and long-term topical authority.
