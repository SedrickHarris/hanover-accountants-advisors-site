# Schema Plan

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the structured data and schema strategy for the Hanover Accountants & Advisors website rebuild.

The schema plan supports:

* SEO
* GEO
* AEO
* Local intent SERPs
* Nationwide service visibility
* LLM search visibility
* ChatGPT discovery
* Perplexity discovery
* Google Search Console validation
* Bing Webmaster indexing
* Rich snippets
* Featured snippets
* People Also Ask support
* Knowledge panel signals
* Google Business Profile alignment
* Apple Search and Apple Business Connect alignment
* Internal entity clarity
* Trust and conversion

Schema must be accurate, visible-content-aligned, and based on verified information.

Do not invent structured data that is not supported by visible page content or verified business facts.

---

# 1. Core Schema Philosophy

Schema should help search engines and AI systems understand:

```txt
Who Hanover is
What Hanover offers
Who Hanover serves
Where Hanover provides services
Which services are available nationwide
Which markets are physical offices or service areas
How pages relate to each other
What questions each page answers
How users can contact or request consultation
```

Schema should not be used to create fake authority, fake reviews, fake local presence, fake pricing, or unsupported business claims.

## Core Rule

Structured data must match the visible content on the page.

If the page does not visibly show a claim, do not mark it up.

If a business fact is not verified, do not include it in schema.

---

# 2. Schema Formats

Use JSON-LD for all structured data.

Recommended component:

```txt
src/components/schema/JsonLd.tsx
```

Recommended schema utilities:

```txt
src/data/schema.ts
src/lib/schema.ts
```

Preferred output format:

```tsx
<script
  type="application/ld+json"
  dangerouslySetInnerHTML={{
    __html: JSON.stringify(schemaObject),
  }}
/>
```

The implementation should avoid duplicate schema blocks and should keep each schema object clean, accurate, and page-specific.

---

# 3. Global Schema Types

Use these schema types across the site where appropriate:

```txt
Organization
AccountingService
ProfessionalService
WebSite
SiteNavigationElement
BreadcrumbList
Service
FAQPage
Article
BlogPosting
LocalBusiness
PostalAddress
ContactPoint
```

## Important Type Notes

Use `Organization` as the core business entity.

Use `AccountingService` or `ProfessionalService` for business classification where appropriate.

Use `LocalBusiness` only for verified physical office pages.

Use `Service` for service pages, nationwide + service pages, audience + service pages, and local + service pages.

Use `FAQPage` only where the page includes visible FAQ content.

Use `Article` or `BlogPosting` for resource articles.

Use `BreadcrumbList` on all pages except the homepage.

---

# 4. Global Organization Schema

## Use On

Use global Organization schema on:

```txt
Homepage
About page
Contact page
Service hubs
Major hub pages
```

The homepage can include the most complete Organization schema.

Other pages can use a shorter version or reference the global entity through `@id`.

## Recommended Entity ID

```txt
https://www.hanoveraa.com/#organization
```

## Required Fields

```txt
@context
@type
@id
name
url
description
telephone
email
address, only verified office address
areaServed
sameAs, only approved social/profile links
```

## Recommended Organization Schema Example

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://www.hanoveraa.com/#organization",
  "name": "Hanover Accountants & Advisors",
  "url": "https://www.hanoveraa.com/",
  "description": "Hanover Accountants & Advisors provides nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services through secure technology and dedicated professionals.",
  "telephone": "404-952-6800",
  "email": "sales@hanoveraa.com",
  "areaServed": {
    "@type": "Country",
    "name": "United States"
  }
}
```

## Fields Requiring Confirmation

Before launch, confirm:

```txt
Final business name
Final public phone number
Final public email address
Final office addresses
Final social profile URLs
Final client portal URL
```

Do not include unverified social links, credentials, awards, or memberships.

---

# 5. Website Schema

## Use On

Use `WebSite` schema on the homepage.

## Recommended Entity ID

```txt
https://www.hanoveraa.com/#website
```

## Recommended WebSite Schema Example

```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "@id": "https://www.hanoveraa.com/#website",
  "name": "Hanover Accountants & Advisors",
  "url": "https://www.hanoveraa.com/",
  "publisher": {
    "@id": "https://www.hanoveraa.com/#organization"
  }
}
```

Do not add a site search action unless the site includes a working internal search feature.

---

# 6. Breadcrumb Schema

## Use On

Use `BreadcrumbList` schema on all pages except the homepage.

## Page Types

Use breadcrumb schema on:

```txt
Service pages
Service category hubs
Audience pages
Audience + service pages
Nationwide service pages
Local service-area pages
Local + service pages
Industry pages
Resource category pages
Resource article pages
FAQ pages
Contact pages
Conversion pages
Legal pages
```

## Example: Service Page Breadcrumb

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://www.hanoveraa.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Services",
      "item": "https://www.hanoveraa.com/services/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Online Bookkeeping",
      "item": "https://www.hanoveraa.com/services/online-bookkeeping/"
    }
  ]
}
```

## Breadcrumb Examples by Page Type

Service page:

```txt
Home > Services > Online Bookkeeping
```

Audience page:

```txt
Home > Who We Help > Startups
```

Audience + service page:

```txt
Home > Who We Help > Startups > Online Bookkeeping
```

Nationwide + service page:

```txt
Home > Service Areas > Nationwide > Tax Preparation
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

# 7. Service Schema

## Use On

Use `Service` schema on:

```txt
/services/[service]
/service-areas/nationwide/[service]
/service-areas/[location]/[service]
/who-we-help/[audience]/[service]
/industries/[industry]/[service], if built
```

## Required Fields

```txt
@context
@type
@id
name
description
provider
areaServed
serviceType
url
```

## General Service Page Example

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "@id": "https://www.hanoveraa.com/services/online-bookkeeping/#service",
  "name": "Online Bookkeeping Services",
  "description": "Online bookkeeping services for businesses that need organized records, reconciled accounts, and clearer financial visibility through secure online workflows.",
  "serviceType": "Online Bookkeeping",
  "provider": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "areaServed": {
    "@type": "Country",
    "name": "United States"
  },
  "url": "https://www.hanoveraa.com/services/online-bookkeeping/"
}
```

## Service Schema Rules

Do not include:

```txt
Fake ratings
Fake reviews
Fake pricing
Fake offers
Fake guarantees
Fake service hours
Fake locations
```

Only include `offers` if pricing or consultation offer details are explicitly approved and visibly shown on the page.

---

# 8. Nationwide Service Schema

## Use On

Use for:

```txt
/service-areas/nationwide/[service]
```

## Area Served

Use:

```json
{
  "@type": "Country",
  "name": "United States"
}
```

## Example

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "@id": "https://www.hanoveraa.com/service-areas/nationwide/tax-preparation/#service",
  "name": "Nationwide Tax Preparation Services",
  "description": "Hanover provides tax preparation services nationwide through secure online workflows, professional review, e-signature, and e-filing support.",
  "serviceType": "Tax Preparation",
  "provider": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "areaServed": {
    "@type": "Country",
    "name": "United States"
  },
  "url": "https://www.hanoveraa.com/service-areas/nationwide/tax-preparation/"
}
```

## Nationwide Schema Rule

Do not imply Hanover has offices nationwide.

Use nationwide `areaServed` for service availability, not physical presence.

---

# 9. Local Service-Area Schema

Local service-area pages require careful handling.

## Two Types of Local Pages

```txt
Verified physical office pages
Service-area pages without physical offices
```

## Verified Physical Office Pages

Use `LocalBusiness`, `AccountingService`, or `ProfessionalService` only when the office is verified.

Known verified or likely verified:

```txt
/service-areas/atlanta-ga
```

Needs confirmation:

```txt
/service-areas/alexandria-va
/service-areas/richmond-va
```

Do not use physical office schema for:

```txt
/service-areas/vinings-ga
/service-areas/sandy-springs-ga
/service-areas/marietta-ga
/service-areas/smyrna-ga
/service-areas/buckhead-atlanta-ga
/service-areas/arlington-va
/service-areas/fairfax-va
```

unless the client confirms physical offices.

---

# 10. LocalBusiness Schema

## Use On

Use only on verified physical office pages.

Potential use:

```txt
/service-areas/atlanta-ga
```

Only use for Alexandria or Richmond after client confirmation.

## Required Fields

```txt
@context
@type
@id
name
url
telephone
address
areaServed
parentOrganization
```

## Recommended Atlanta Schema Example

```json
{
  "@context": "https://schema.org",
  "@type": "AccountingService",
  "@id": "https://www.hanoveraa.com/service-areas/atlanta-ga/#localbusiness",
  "name": "Hanover Accountants & Advisors - Atlanta, GA",
  "url": "https://www.hanoveraa.com/service-areas/atlanta-ga/",
  "telephone": "404-952-6800",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "2727 Paces Ferry Road SE, Suite 1-750",
    "addressLocality": "Atlanta",
    "addressRegion": "GA",
    "postalCode": "30339",
    "addressCountry": "US"
  },
  "areaServed": [
    {
      "@type": "City",
      "name": "Atlanta"
    },
    {
      "@type": "State",
      "name": "Georgia"
    }
  ],
  "parentOrganization": {
    "@id": "https://www.hanoveraa.com/#organization"
  }
}
```

## LocalBusiness Rules

Do not include:

```txt
Coordinates unless verified
Business hours unless verified
Department schema unless verified
Aggregate ratings unless verified and visible
Reviews unless verified, approved, and visible
Price range unless approved
```

---

# 11. Service-Area Pages Without Physical Office Schema

For pages representing served markets, use `Service`, `AreaServed`, `FAQPage`, and `BreadcrumbList`.

## Example: Sandy Springs Service-Area Page

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "@id": "https://www.hanoveraa.com/service-areas/sandy-springs-ga/#service-area",
  "name": "Accounting, Tax, Bookkeeping, Payroll and Advisory Services in Sandy Springs, GA",
  "description": "Hanover serves clients in Sandy Springs, GA with online accounting, tax, bookkeeping, payroll, and advisory services through secure online workflows.",
  "provider": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "areaServed": {
    "@type": "City",
    "name": "Sandy Springs"
  },
  "url": "https://www.hanoveraa.com/service-areas/sandy-springs-ga/"
}
```

## Service-Area Rule

Do not use fake office language or fake LocalBusiness markup for service-area-only pages.

---

# 12. Local + Service Schema

## Use On

Use for:

```txt
/service-areas/[location]/[service]
```

## Schema Type

Use `Service`.

Use `areaServed` for the city or market.

## Example

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "@id": "https://www.hanoveraa.com/service-areas/atlanta-ga/tax-preparation/#service",
  "name": "Tax Preparation in Atlanta, GA",
  "description": "Hanover provides tax preparation for clients in Atlanta, GA through secure online workflows, professional review, e-signature, and e-filing support.",
  "serviceType": "Tax Preparation",
  "provider": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "areaServed": {
    "@type": "City",
    "name": "Atlanta"
  },
  "url": "https://www.hanoveraa.com/service-areas/atlanta-ga/tax-preparation/"
}
```

## Local + Service Schema Rule

If the local page is not a verified office page, do not use `LocalBusiness`.

Use `Service` with `areaServed`.

---

# 13. Audience + Service Schema

## Use On

Use for:

```txt
/who-we-help/[audience]/[service]
```

## Schema Type

Use `Service`.

## Example

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "@id": "https://www.hanoveraa.com/who-we-help/startups/online-bookkeeping/#service",
  "name": "Online Bookkeeping for Startups",
  "description": "Hanover provides online bookkeeping for startups through secure workflows and professional support for organized financial records and clearer reporting.",
  "serviceType": "Online Bookkeeping",
  "provider": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "audience": {
    "@type": "Audience",
    "audienceType": "Startups"
  },
  "areaServed": {
    "@type": "Country",
    "name": "United States"
  },
  "url": "https://www.hanoveraa.com/who-we-help/startups/online-bookkeeping/"
}
```

## Audience Schema Rule

Use audience markup only where the page clearly targets that audience.

Do not invent audience claims beyond what the page visibly supports.

---

# 14. Industry Page Schema

## Use On

Use for:

```txt
/industries/[industry]
/industries/[industry]/[service], if built
```

## Recommended Schema

Use `Service` or `CollectionPage` depending on page structure.

If the page is a service-oriented industry page, use `Service`.

If the page is a hub-style industry overview, use `CollectionPage` with related services.

## Example Industry Service Schema

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "@id": "https://www.hanoveraa.com/industries/construction/#service",
  "name": "Accounting, Tax and Advisory Services for Construction Businesses",
  "description": "Hanover supports construction businesses with accounting, tax, payroll, reporting, cash flow, and advisory services through secure online workflows.",
  "serviceType": "Accounting and Advisory Services",
  "provider": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "audience": {
    "@type": "BusinessAudience",
    "audienceType": "Construction Businesses"
  },
  "areaServed": {
    "@type": "Country",
    "name": "United States"
  },
  "url": "https://www.hanoveraa.com/industries/construction/"
}
```

---

# 15. FAQPage Schema

## Use On

Use `FAQPage` schema when the page includes visible FAQ questions and answers.

Use on:

```txt
Service pages
Audience pages
Audience + service pages
Nationwide service pages
Local service-area pages
Local + service pages
Industry pages
Resource pages, where appropriate
FAQ category pages
```

## Requirements

Only mark up FAQs that are visible on the page.

Do not mark up hidden questions.

Do not mark up promotional content as FAQs.

Do not mark up questions and answers that are not visible to users.

## Example

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "@id": "https://www.hanoveraa.com/services/tax-preparation/#faq",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Can Hanover prepare taxes online?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Hanover provides online tax preparation through secure document upload, professional review, e-signature, and e-filing support."
      }
    },
    {
      "@type": "Question",
      "name": "How do I share my tax documents?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Clients can use Hanover's secure online workflow to share tax documents and complete the information needed for review and preparation."
      }
    }
  ]
}
```

## FAQ Schema Note

FAQ schema can still help clarify page structure and entities, but rich-result visibility is not guaranteed.

---

# 16. Article and BlogPosting Schema

## Use On

Use for:

```txt
/resources/[category]/[slug]
```

## Recommended Type

Use `Article` for evergreen guides.

Use `BlogPosting` only if the content is treated as a blog post with publication date and author information.

For this project, default to `Article`.

## Required Fields

```txt
@context
@type
@id
headline
description
author or publisher
publisher
datePublished, if known
dateModified, if known
mainEntityOfPage
url
```

## Example

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "@id": "https://www.hanoveraa.com/resources/bookkeeping/what-is-online-bookkeeping/#article",
  "headline": "What Is Online Bookkeeping?",
  "description": "A plain-English guide explaining online bookkeeping, how it works, what it includes, and when a business may need support.",
  "author": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "publisher": {
    "@id": "https://www.hanoveraa.com/#organization"
  },
  "mainEntityOfPage": "https://www.hanoveraa.com/resources/bookkeeping/what-is-online-bookkeeping/",
  "url": "https://www.hanoveraa.com/resources/bookkeeping/what-is-online-bookkeeping/"
}
```

## Article Schema Rule

Do not invent individual authors.

Use Organization as author or publisher unless Hanover approves named authors.

---

# 17. ContactPoint Schema

## Use On

Use inside Organization schema or Contact page schema if contact information is verified.

## Example

```json
{
  "@type": "ContactPoint",
  "telephone": "404-952-6800",
  "contactType": "customer service",
  "areaServed": "US",
  "availableLanguage": "English"
}
```

## ContactPoint Rules

Do not include:

```txt
Unverified phone numbers
Unverified hours
Unverified departments
Unverified languages
Unverified support types
```

---

# 18. SiteNavigationElement Schema

## Use On

Use on homepage or globally if useful.

## Recommended Navigation Items

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

## Example

```json
{
  "@context": "https://schema.org",
  "@type": "SiteNavigationElement",
  "name": "Services",
  "url": "https://www.hanoveraa.com/services/"
}
```

## Implementation Note

This schema is optional. Do not overcomplicate if navigation is already clear in HTML.

---

# 19. Schema by Page Type

## Homepage

Use:

```txt
Organization
WebSite
SiteNavigationElement, optional
```

## About Page

Use:

```txt
Organization
BreadcrumbList
```

## Contact Page

Use:

```txt
Organization
ContactPoint
BreadcrumbList
```

## Services Hub

Use:

```txt
CollectionPage
BreadcrumbList
```

## Service Category Hubs

Use:

```txt
CollectionPage
BreadcrumbList
```

## Individual Service Pages

Use:

```txt
Service
FAQPage
BreadcrumbList
```

## Audience Pages

Use:

```txt
CollectionPage or Service
FAQPage
BreadcrumbList
```

## Audience + Service Pages

Use:

```txt
Service
FAQPage
BreadcrumbList
```

## Service Areas Hub

Use:

```txt
CollectionPage
BreadcrumbList
```

## Nationwide Service Area Page

Use:

```txt
Service
FAQPage
BreadcrumbList
```

## Nationwide + Service Pages

Use:

```txt
Service
FAQPage
BreadcrumbList
```

## Verified Physical Office Pages

Use:

```txt
AccountingService or LocalBusiness
PostalAddress
FAQPage
BreadcrumbList
```

## Service-Area-Only Pages

Use:

```txt
Service
AreaServed
FAQPage
BreadcrumbList
```

## Local + Service Pages

Use:

```txt
Service
AreaServed
FAQPage
BreadcrumbList
```

## Industry Pages

Use:

```txt
Service or CollectionPage
FAQPage
BreadcrumbList
```

## Resource Category Pages

Use:

```txt
CollectionPage
BreadcrumbList
```

## Resource Articles

Use:

```txt
Article
FAQPage, if visible FAQs are included
BreadcrumbList
```

## FAQ Pages

Use:

```txt
FAQPage
BreadcrumbList
```

---

# 20. Schema Data File Structure

Recommended files:

```txt
src/data/schema.ts
src/lib/schema.ts
src/components/schema/JsonLd.tsx
```

## `src/data/schema.ts`

Use for base entity data:

```ts
export const organizationSchemaBase = {
  name: "Hanover Accountants & Advisors",
  url: "https://www.hanoveraa.com/",
  telephone: "404-952-6800",
  email: "sales@hanoveraa.com",
};
```

## `src/lib/schema.ts`

Use for schema generators:

```txt
buildOrganizationSchema()
buildWebsiteSchema()
buildBreadcrumbSchema()
buildServiceSchema()
buildLocalBusinessSchema()
buildFaqSchema()
buildArticleSchema()
buildCollectionPageSchema()
```

## `src/components/schema/JsonLd.tsx`

Use for rendering:

```tsx
type JsonLdProps = {
  data: Record<string, unknown> | Record<string, unknown>[];
};

export function JsonLd({ data }: JsonLdProps) {
  return (
    <script
      type="application/ld+json"
      dangerouslySetInnerHTML={{
        __html: JSON.stringify(data),
      }}
    />
  );
}
```

---

# 21. Entity ID Strategy

Use stable `@id` values.

## Recommended IDs

```txt
Organization: https://www.hanoveraa.com/#organization
Website: https://www.hanoveraa.com/#website
Service page: https://www.hanoveraa.com/services/[service]/#service
FAQ block: https://www.hanoveraa.com/[path]/#faq
Breadcrumb: https://www.hanoveraa.com/[path]/#breadcrumb
Article: https://www.hanoveraa.com/resources/[category]/[slug]/#article
Local office: https://www.hanoveraa.com/service-areas/[location]/#localbusiness
```

Stable IDs help keep the site's entity graph consistent.

---

# 22. Do Not Use Schema For

Do not add schema for:

```txt
Fake reviews
Fake ratings
Fake aggregate ratings
Fake pricing
Fake offers
Fake awards
Fake credentials
Fake certifications
Fake office locations
Fake business hours
Fake coordinates
Fake team members
Fake authors
Unsupported software claims
Unsupported guarantees
Unsupported tax outcomes
```

Do not mark up content that is not visible on the page.

Do not use structured data to make claims stronger than the visible copy.

---

# 23. Review Schema Rule

Do not use review schema or aggregate rating schema unless all of the following are true:

```txt
The review is real.
The review is approved by the client.
The review is visible on the page.
The markup accurately reflects the visible review.
The page is allowed to use review markup under current guidance.
```

Default rule:

```txt
Do not implement review or aggregate rating schema for launch.
```

---

# 24. Offer and Pricing Schema Rule

Do not use `Offer`, `price`, `priceRange`, or package markup unless Hanover approves public pricing.

Default rule:

```txt
Do not implement pricing schema for launch.
```

Use consultation-focused CTAs instead.

---

# 25. Physical Office Schema Rule

Only use physical office schema when the office is confirmed.

## Confirm Before Launch

```txt
Atlanta office address
Atlanta phone number
Virginia office address
Richmond vs Alexandria language
Business hours
Which offices connect to GBP
Which offices connect to Apple Business Connect
```

If not confirmed, use service-area language and service-area schema.

---

# 26. Schema Validation Workflow

Before launch, test schema using:

```txt
Google Rich Results Test
Schema Markup Validator
Google Search Console URL Inspection after indexing
```

## Validation Checklist

```txt
No JSON-LD syntax errors
No missing required fields
No fake reviews
No fake prices
No fake office claims
No duplicate Organization entities with conflicting data
Breadcrumbs match visible breadcrumbs
FAQ schema matches visible FAQs
Service schema matches visible service content
LocalBusiness schema only appears on verified office pages
Article schema only appears on resource articles
```

---

# 27. Schema and Sitemap Alignment

Every indexable page should have:

```txt
Canonical URL
Sitemap entry
Breadcrumb schema
Metadata
Relevant structured data
Internal links
```

Do not include schema for pages that are noindexed, blocked, or intentionally hidden from search.

---

# 28. Schema and Internal Linking Alignment

Structured data should reflect the site's internal linking and content architecture.

Example:

```txt
/services/tax-preparation
```

Should link to and/or relate to:

```txt
/services/tax
/services/tax-planning
/services/tax-compliance
/service-areas/nationwide/tax-preparation
/who-we-help/small-businesses/tax-preparation
/faqs/tax-preparation
/resources/tax-preparation/online-tax-preparation-checklist
/schedule-consultation
```

The schema, breadcrumbs, page copy, and internal links should all reinforce the same topic.

---

# 29. Implementation Priority

## Phase 1 Schema

Implement:

```txt
Organization
WebSite
BreadcrumbList
Service
FAQPage
Article
CollectionPage
```

## Phase 2 Schema

Implement:

```txt
Nationwide service schema
Local service-area schema
Local + service schema
Audience + service schema
Industry schema
```

## Phase 3 Schema

Implement:

```txt
Verified LocalBusiness schema
ContactPoint schema
SiteNavigationElement schema, optional
```

Do not implement review, rating, pricing, or offer schema unless approved.

---

# 30. Final Schema Direction

The Hanover site should use schema to clarify, not exaggerate.

The structured data should support:

```txt
Business identity
Nationwide service availability
Service offerings
Audience-specific service pages
Local service-area pages
Verified physical office pages
Educational resources
FAQs
Breadcrumbs
Internal topic relationships
```

The schema must remain accurate, visible-content-aligned, and safe for a professional accounting, tax, and advisory website.

Do not use schema to invent trust signals, locations, ratings, credentials, or results.
