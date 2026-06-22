# Metadata Plan

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the metadata strategy for the Hanover Accountants & Advisors website rebuild.

The metadata plan supports:

* SEO
* GEO
* AEO
* Local intent SERPs
* Nationwide service visibility
* Audience-specific search intent
* Google Search Console indexing
* Bing Webmaster indexing
* Apple Search visibility
* LLM search clarity
* Featured snippets
* People Also Ask support
* Rich snippet readiness
* Social sharing
* Customer engagement
* Customer conversion

Every indexable page must have unique, useful, accurate, human-readable metadata.

---

# 1. Metadata Philosophy

Metadata should clearly communicate:

```txt
What the page is about
Who the page is for
Where the service is available, when relevant
Why the page is useful
What the visitor can do next
```

Metadata should be written for people first and search engines second.

Do not keyword stuff.

Do not duplicate title tags or meta descriptions across matrix pages.

Do not make claims that are not supported by the page content.

Do not include fake pricing, fake guarantees, fake reviews, or fake office claims.

---

# 2. Metadata Fields Required

Every indexable page should include:

```txt
Title tag
Meta description
Canonical URL
Open Graph title
Open Graph description
Open Graph URL
Open Graph image
Twitter card metadata, if used
Robots directive
Single H1
Breadcrumbs
Schema alignment
```

## Recommended Next.js Metadata Fields

```ts
export const metadata = {
  title: "",
  description: "",
  alternates: {
    canonical: "",
  },
  openGraph: {
    title: "",
    description: "",
    url: "",
    siteName: "Hanover Accountants & Advisors",
    type: "website",
    images: [
      {
        url: "/images/og/hanover-default-og.jpg",
        width: 1200,
        height: 630,
        alt: "Hanover Accountants & Advisors",
      },
    ],
  },
  robots: {
    index: true,
    follow: true,
  },
};
```

---

# 3. Global Metadata Defaults

## Site Name

```txt
Hanover Accountants & Advisors
```

## Default Title Pattern

```txt
[Page Topic] | Hanover Accountants & Advisors
```

## Default Description Pattern

```txt
Hanover provides [service/topic] through secure online workflows and professional support. Schedule a consultation for accounting, tax, bookkeeping, payroll, or advisory help.
```

## Default Canonical Base

```txt
https://www.hanoveraa.com
```

## Default Open Graph Image

```txt
/images/og/hanover-default-og.jpg
```

## Default Robots Rule

```txt
index, follow
```

---

# 4. Title Tag Rules

## Recommended Length

Title tags should usually be:

```txt
45 to 65 characters
```

This is a practical target, not a hard rule.

## Title Tag Rules

Use:

```txt
Clear page topic
Service name where relevant
Audience where relevant
Location where relevant
Brand name at the end
```

Avoid:

```txt
Keyword stuffing
Repeated service terms
Fake urgency
Fake pricing
Excessively long city lists
Unverified credentials
Unverified awards
```

## Good Examples

```txt
Online Bookkeeping Services | Hanover Accountants & Advisors
Tax Preparation for Small Businesses | Hanover Accountants & Advisors
Payroll Services in Atlanta, GA | Hanover Accountants & Advisors
Nationwide Outsourced CFO Services | Hanover Accountants & Advisors
```

## Bad Examples

```txt
Best Cheap Accounting Tax CPA Bookkeeping Payroll CFO Services Nationwide USA
#1 Atlanta Tax Preparation Experts Guaranteed Maximum Refund
Affordable Bookkeeping Atlanta Marietta Smyrna Sandy Springs Vinings
```

---

# 5. Meta Description Rules

## Recommended Length

Meta descriptions should usually be:

```txt
140 to 160 characters
```

They can be slightly longer if clarity requires it.

## Description Rules

Use:

```txt
Plain-English summary
Service, audience, or location context
Secure online workflow language where relevant
Consultation CTA
Accurate claims only
```

Avoid:

```txt
Keyword stuffing
Unverified prices
Guarantees
Fake urgency
Fake claims
Excessive punctuation
Duplicate descriptions
```

## Good Examples

```txt
Hanover provides online bookkeeping services for businesses that need organized records, reconciliations, reporting support, and secure professional help.
```

```txt
Hanover provides tax preparation for small businesses through secure online workflows, professional review, and consultation-based support.
```

```txt
Hanover serves clients in Atlanta, GA with online accounting, bookkeeping, tax preparation, payroll, and advisory services.
```

## Bad Examples

```txt
Best tax prep in Atlanta. Guaranteed refund. Cheapest bookkeeping and payroll services. Call now before it is too late.
```

```txt
Hanover is the number one accounting firm in America with the best CPAs and guaranteed tax savings for every client.
```

---

# 6. H1 Rules

Every page must have one clear H1.

The H1 should closely align with the page topic and title tag.

## H1 Examples

Service page:

```txt
Online Bookkeeping Services
```

Audience page:

```txt
Accounting, Tax & Advisory Services for Startups
```

Audience + service page:

```txt
Online Bookkeeping for Startups
```

Nationwide page:

```txt
Nationwide Online Accounting, Tax, Bookkeeping & Advisory Services
```

Local + service page:

```txt
Tax Preparation in Atlanta, GA
```

Resource article:

```txt
What Is Online Bookkeeping?
```

---

# 7. Canonical URL Rules

Every indexable page should self-canonicalize.

## Canonical Format

Use trailing slash if the static export uses trailing slash.

```txt
https://www.hanoveraa.com/services/online-bookkeeping/
```

## Matrix Page Canonical Rule

Do not canonicalize useful, unique matrix pages back to broad pages.

For example, this page:

```txt
/service-areas/atlanta-ga/tax-preparation
```

Should canonical to:

```txt
https://www.hanoveraa.com/service-areas/atlanta-ga/tax-preparation/
```

Not to:

```txt
https://www.hanoveraa.com/services/tax-preparation/
```

If the matrix page is individually written and useful, it should self-canonicalize.

---

# 8. Robots Metadata Rules

Most pages should be:

```txt
index, follow
```

Use `noindex` only for:

```txt
Draft pages
Testing pages
Duplicate utility pages
Thank-you pages, if used
Internal-only pages
Temporary pages not ready for search
```

Do not noindex local pages just because they are part of a matrix.

If they are unique and useful, they should be indexable.

---

# 9. Open Graph Metadata Rules

Every major page should include Open Graph metadata.

## Required Open Graph Fields

```txt
og:title
og:description
og:url
og:site_name
og:type
og:image
```

## Default OG Type

Use:

```txt
website
```

For resource articles, use:

```txt
article
```

## OG Image Strategy

Default OG image:

```txt
/images/og/hanover-default-og.jpg
```

Optional section-specific OG images:

```txt
/images/og/services-og.jpg
/images/og/tax-og.jpg
/images/og/bookkeeping-og.jpg
/images/og/advisory-og.jpg
/images/og/nationwide-og.jpg
/images/og/service-areas-og.jpg
/images/og/resources-og.jpg
```

## OG Image Size

Recommended:

```txt
1200 x 630
```

---

# 10. Metadata by Page Type

## Homepage

### Title Pattern

```txt
Online Accounting, Tax & Advisory Services | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover provides nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services through secure professional support.
```

### H1 Pattern

```txt
Online Accounting, Tax, Bookkeeping & Advisory Services for Businesses Nationwide
```

---

## About Page

### Title Pattern

```txt
About Hanover Accountants & Advisors
```

### Description Pattern

```txt
Learn about Hanover Accountants & Advisors, a professional accounting, tax, bookkeeping, and advisory firm serving clients through secure online workflows.
```

### H1 Pattern

```txt
About Hanover Accountants & Advisors
```

---

## Contact Page

### Title Pattern

```txt
Contact Hanover Accountants & Advisors
```

### Description Pattern

```txt
Contact Hanover Accountants & Advisors to schedule a consultation for accounting, tax preparation, bookkeeping, payroll, or advisory services.
```

### H1 Pattern

```txt
Contact Hanover Accountants & Advisors
```

---

## Services Hub

### Title Pattern

```txt
Accounting, Tax & Advisory Services | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Explore Hanover's online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and business advisory services.
```

### H1 Pattern

```txt
Accounting, Tax, Bookkeeping & Advisory Services
```

---

## Service Category Hubs

### Title Pattern

```txt
[Category Name] | Hanover Accountants & Advisors
```

Examples:

```txt
Accounting Services | Hanover Accountants & Advisors
Tax Services | Hanover Accountants & Advisors
Advisory Services | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Explore Hanover's [category] services for clients who need secure online support, professional guidance, and consultation-based service planning.
```

### H1 Pattern

```txt
[Category Name]
```

---

## Individual Service Pages

### Title Pattern

```txt
[Service Name] | Hanover Accountants & Advisors
```

Examples:

```txt
Online Bookkeeping Services | Hanover Accountants & Advisors
Tax Preparation Services | Hanover Accountants & Advisors
Outsourced CFO Services | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover provides [service name] through secure online workflows and professional support. Schedule a consultation for accounting, tax, payroll, or advisory help.
```

### H1 Pattern

```txt
[Service Name]
```

---

## Audience Hub

### Title Pattern

```txt
Who We Help | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover serves individuals, entrepreneurs, startups, small businesses, family-owned businesses, business owners, and growing companies.
```

### H1 Pattern

```txt
Who We Help
```

---

## Audience Pages

### Title Pattern

```txt
Accounting, Tax & Advisory Services for [Audience] | Hanover
```

Alternative if the title is too long:

```txt
Services for [Audience] | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover helps [audience] manage accounting, bookkeeping, tax, payroll, reporting, and advisory needs through secure online services.
```

### H1 Pattern

```txt
Accounting, Tax & Advisory Services for [Audience]
```

---

## Audience + Service Pages

### Title Pattern

```txt
[Service Name] for [Audience] | Hanover Accountants & Advisors
```

Examples:

```txt
Online Bookkeeping for Startups | Hanover Accountants & Advisors
Tax Preparation for Small Businesses | Hanover Accountants & Advisors
Outsourced CFO Services for Family-Owned Businesses | Hanover
```

### Description Pattern

```txt
Hanover provides [service name] for [audience] through secure online workflows and professional support. Schedule a consultation to discuss your needs.
```

### H1 Pattern

```txt
[Service Name] for [Audience]
```

---

## Service Areas Hub

### Title Pattern

```txt
Service Areas | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover provides nationwide online accounting, tax, bookkeeping, payroll, and advisory services with service-area support in Georgia and Virginia markets.
```

### H1 Pattern

```txt
Nationwide and Local Service Areas
```

---

## Nationwide Service Area Page

### Title Pattern

```txt
Nationwide Online Accounting & Tax Services | Hanover
```

### Description Pattern

```txt
Hanover provides nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services through secure workflows.
```

### H1 Pattern

```txt
Nationwide Online Accounting, Tax, Bookkeeping & Advisory Services
```

---

## Nationwide + Service Pages

### Title Pattern

```txt
Nationwide [Service Name] | Hanover Accountants & Advisors
```

Examples:

```txt
Nationwide Online Bookkeeping Services | Hanover
Nationwide Tax Preparation Services | Hanover
Nationwide Outsourced CFO Services | Hanover
```

### Description Pattern

```txt
Hanover provides nationwide [service name] through secure online workflows and professional support. Schedule a consultation to discuss your needs.
```

### H1 Pattern

```txt
Nationwide [Service Name]
```

---

## Local Service-Area Pages

### Title Pattern

```txt
Accounting, Tax & Advisory Services in [City, State] | Hanover
```

Examples:

```txt
Accounting, Tax & Advisory Services in Atlanta, GA | Hanover
Accounting, Tax & Advisory Services in Alexandria, VA | Hanover
```

### Description Pattern

```txt
Hanover serves clients in [city, state] with online accounting, bookkeeping, tax preparation, payroll, and advisory services.
```

### H1 Pattern

```txt
Accounting, Tax & Advisory Services in [City, State]
```

---

## Local + Service Pages

### Title Pattern

```txt
[Service Name] in [City, State] | Hanover Accountants & Advisors
```

Examples:

```txt
Tax Preparation in Atlanta, GA | Hanover Accountants & Advisors
Online Bookkeeping in Alexandria, VA | Hanover Accountants & Advisors
Payroll Services in Sandy Springs, GA | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover provides [service name] for clients in [city, state] through secure online workflows and professional support. Schedule a consultation.
```

### H1 Pattern

```txt
[Service Name] in [City, State]
```

---

## Industry Hub

### Title Pattern

```txt
Industries Served | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Hanover supports businesses across industries with online accounting, tax, payroll, reporting, outsourced CFO, and advisory services.
```

### H1 Pattern

```txt
Industries Served
```

---

## Industry Pages

### Title Pattern

```txt
Accounting, Tax & Advisory Services for [Industry] | Hanover
```

Examples:

```txt
Accounting Services for Construction Businesses | Hanover
Tax & Advisory Services for Professional Services Firms | Hanover
```

### Description Pattern

```txt
Hanover supports [industry] with accounting, bookkeeping, tax, payroll, reporting, and advisory services through secure online workflows.
```

### H1 Pattern

```txt
Accounting, Tax & Advisory Services for [Industry]
```

---

## Resource Hub

### Title Pattern

```txt
Accounting, Tax & Business Finance Resources | Hanover
```

### Description Pattern

```txt
Explore accounting, tax, bookkeeping, payroll, CFO advisory, and business finance resources from Hanover Accountants & Advisors.
```

### H1 Pattern

```txt
Accounting, Tax & Business Finance Resources
```

---

## Resource Category Pages

### Title Pattern

```txt
[Category] Resources | Hanover Accountants & Advisors
```

Examples:

```txt
Bookkeeping Resources | Hanover Accountants & Advisors
Tax Planning Resources | Hanover Accountants & Advisors
Payroll Resources | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Explore Hanover resources about [category topic], including plain-English guides, checklists, FAQs, and related service information.
```

### H1 Pattern

```txt
[Category] Resources
```

---

## Resource Article Pages

### Title Pattern

```txt
[Article Title] | Hanover Accountants & Advisors
```

Examples:

```txt
What Is Online Bookkeeping? | Hanover Accountants & Advisors
Year-End Tax Planning Checklist | Hanover Accountants & Advisors
When to Hire an Outsourced CFO | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Learn [article topic] in plain English, including what it means, why it matters, and when to consider professional accounting or advisory support.
```

### H1 Pattern

```txt
[Article Title]
```

---

## FAQ Hub

### Title Pattern

```txt
Accounting, Tax & Advisory FAQs | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Find answers to common questions about Hanover's accounting, tax preparation, bookkeeping, payroll, advisory, and nationwide services.
```

### H1 Pattern

```txt
Frequently Asked Questions
```

---

## FAQ Category Pages

### Title Pattern

```txt
[Topic] FAQs | Hanover Accountants & Advisors
```

Examples:

```txt
Online Bookkeeping FAQs | Hanover Accountants & Advisors
Tax Preparation FAQs | Hanover Accountants & Advisors
Nationwide Services FAQs | Hanover Accountants & Advisors
```

### Description Pattern

```txt
Find answers to common questions about [topic], how Hanover's online process works, and when to schedule a consultation.
```

### H1 Pattern

```txt
[Topic] FAQs
```

---

# 11. Metadata Data Model

Recommended file:

```txt
src/data/metadata.ts
```

Metadata may also be stored directly inside page data objects:

```txt
src/data/services.ts
src/data/audiences.ts
src/data/audienceServiceMatrix.ts
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
src/data/industries.ts
src/data/resources.ts
src/data/faqs.ts
```

## Recommended Metadata Type

```ts
export type PageMetadata = {
  title: string;
  description: string;
  canonical: string;
  h1: string;
  ogTitle?: string;
  ogDescription?: string;
  ogImage?: string;
  robots?: {
    index: boolean;
    follow: boolean;
  };
};
```

---

# 12. Metadata Generator Functions

Recommended file:

```txt
src/lib/metadata.ts
```

Recommended functions:

```txt
buildCanonical(path: string)
buildBaseMetadata(page: PageMetadata)
buildServiceMetadata(service)
buildAudienceMetadata(audience)
buildAudienceServiceMetadata(audience, service)
buildNationwideServiceMetadata(service)
buildServiceAreaMetadata(location)
buildLocationServiceMetadata(location, service)
buildIndustryMetadata(industry)
buildResourceMetadata(resource)
buildFaqMetadata(faqCategory)
```

## Example Function Direction

```ts
export function buildCanonical(path: string) {
  const baseUrl = "https://www.hanoveraa.com";
  const cleanPath = path.endsWith("/") ? path : `${path}/`;
  return `${baseUrl}${cleanPath}`;
}
```

---

# 13. Metadata and Schema Alignment

Metadata, visible page content, breadcrumbs, and schema should agree.

Example page:

```txt
/service-areas/atlanta-ga/tax-preparation
```

Should align across:

```txt
Title tag: Tax Preparation in Atlanta, GA | Hanover Accountants & Advisors
H1: Tax Preparation in Atlanta, GA
Canonical: https://www.hanoveraa.com/service-areas/atlanta-ga/tax-preparation/
Schema name: Tax Preparation in Atlanta, GA
Breadcrumb: Home > Service Areas > Atlanta, GA > Tax Preparation
Visible copy: Tax preparation for clients in Atlanta, GA
```

Do not create metadata that says one thing while the page content says another.

---

# 14. Local Metadata Accuracy Rules

For service-area pages without verified offices, avoid office language.

## Safe Metadata

```txt
Accounting, Tax & Advisory Services in Sandy Springs, GA | Hanover
```

```txt
Hanover serves clients in Sandy Springs, GA with online accounting, bookkeeping, tax preparation, payroll, and advisory services.
```

## Unsafe Metadata

```txt
Sandy Springs Accounting Office | Hanover Accountants & Advisors
```

```txt
Visit Hanover's Sandy Springs office for local tax preparation and bookkeeping services.
```

Do not write "office" unless the office is verified.

---

# 15. Nationwide Metadata Rules

Nationwide metadata should emphasize online availability, secure workflows, and professional support.

## Safe Nationwide Metadata

```txt
Nationwide Online Bookkeeping Services | Hanover
```

```txt
Hanover provides nationwide online bookkeeping through secure workflows and professional support for organized records and clearer reporting.
```

## Unsafe Nationwide Metadata

```txt
Hanover Offices Nationwide | Best Accounting Firm in America
```

```txt
Visit one of Hanover's nationwide offices for guaranteed bookkeeping and tax savings.
```

Do not imply physical offices nationwide.

---

# 16. Metadata for Matrix Pages

Matrix pages must have unique metadata.

## Audience + Service Matrix Example

```txt
Online Bookkeeping for Startups | Hanover Accountants & Advisors
```

```txt
Hanover provides online bookkeeping for startups through secure workflows and professional support for organized records and clearer reporting.
```

## Local + Service Matrix Example

```txt
Online Bookkeeping in Marietta, GA | Hanover Accountants & Advisors
```

```txt
Hanover provides online bookkeeping for clients in Marietta, GA through secure online workflows and professional support.
```

## Nationwide + Service Matrix Example

```txt
Nationwide Online Bookkeeping Services | Hanover
```

```txt
Hanover provides nationwide online bookkeeping services through secure workflows and professional support for organized financial records.
```

---

# 17. Duplicate Metadata Prevention

The build must include metadata QA.

Check for:

```txt
Duplicate title tags
Duplicate meta descriptions
Missing title tags
Missing meta descriptions
Duplicate H1s across similar page types
Missing H1s
Wrong canonical URLs
Wrong noindex tags
Wrong OG URLs
Wrong local office language
```

## Data Rule

Every matrix item should define or generate unique metadata based on:

```txt
Service name
Audience name
Location name
Nationwide modifier
Industry name
Resource title
FAQ topic
```

---

# 18. Open Graph Image Strategy

At launch, the site can use a default OG image for all pages.

## Default

```txt
/images/og/hanover-default-og.jpg
```

Later, add section-level OG images:

```txt
/images/og/services-og.jpg
/images/og/accounting-og.jpg
/images/og/tax-og.jpg
/images/og/advisory-og.jpg
/images/og/nationwide-og.jpg
/images/og/service-areas-og.jpg
/images/og/resources-og.jpg
/images/og/faqs-og.jpg
```

Do not use images with fake logos, fake awards, fake badges, or unreadable text.

---

# 19. Metadata QA Checklist

Before launch, verify:

```txt
Every indexable page has a title tag.
Every indexable page has a meta description.
Every indexable page has a canonical URL.
Every indexable page has one H1.
Every indexable page has OG metadata.
Every indexable page has robots index, follow unless intentionally noindexed.
Every title tag is unique.
Every meta description is unique.
Every canonical URL matches the final route.
Every OG URL matches the final route.
Every local page avoids fake office language.
Every nationwide page avoids fake nationwide office language.
Every metadata claim is supported by visible page content.
Every resource article has an article-style title and description.
Every FAQ page has a question-focused title and description.
```

---

# 20. Recommended Metadata Build Order

## Phase 1

Create metadata for:

```txt
Homepage
About
Contact
Schedule Consultation
Get Started
Client Portal
Services Hub
Service Category Hubs
Priority Service Pages
Who We Help Hub
Service Areas Hub
Nationwide Hub
Industries Hub
Resources Hub
FAQ Hub
```

## Phase 2

Create metadata for:

```txt
Nationwide + service pages
Audience pages
Audience + service pages
Local service-area pages
Local + service pages
Industry pages
Resource category pages
Resource articles
FAQ category pages
```

## Phase 3

Run duplicate metadata QA and canonical QA.

---

# 21. Example Metadata Objects

## Service Page Example

```ts
{
  title: "Online Bookkeeping Services | Hanover Accountants & Advisors",
  description:
    "Hanover provides online bookkeeping services for businesses that need organized records, reconciliations, reporting support, and secure professional help.",
  canonical: "https://www.hanoveraa.com/services/online-bookkeeping/",
  h1: "Online Bookkeeping Services",
  ogTitle: "Online Bookkeeping Services",
  ogDescription:
    "Secure online bookkeeping support for organized records, reconciliations, and clearer financial visibility.",
  ogImage: "/images/og/bookkeeping-og.jpg",
  robots: {
    index: true,
    follow: true,
  },
}
```

## Audience + Service Example

```ts
{
  title: "Online Bookkeeping for Startups | Hanover Accountants & Advisors",
  description:
    "Hanover provides online bookkeeping for startups through secure workflows and professional support for organized records and clearer reporting.",
  canonical: "https://www.hanoveraa.com/who-we-help/startups/online-bookkeeping/",
  h1: "Online Bookkeeping for Startups",
  ogTitle: "Online Bookkeeping for Startups",
  ogDescription:
    "Bookkeeping support for startups that need organized records, clearer reporting, and secure online accounting workflows.",
  ogImage: "/images/og/bookkeeping-og.jpg",
  robots: {
    index: true,
    follow: true,
  },
}
```

## Local + Service Example

```ts
{
  title: "Tax Preparation in Atlanta, GA | Hanover Accountants & Advisors",
  description:
    "Hanover provides tax preparation for clients in Atlanta, GA through secure online workflows and professional support. Schedule a consultation.",
  canonical: "https://www.hanoveraa.com/service-areas/atlanta-ga/tax-preparation/",
  h1: "Tax Preparation in Atlanta, GA",
  ogTitle: "Tax Preparation in Atlanta, GA",
  ogDescription:
    "Tax preparation support for Atlanta clients through secure online workflows and professional review.",
  ogImage: "/images/og/tax-og.jpg",
  robots: {
    index: true,
    follow: true,
  },
}
```

## Resource Article Example

```ts
{
  title: "What Is Online Bookkeeping? | Hanover Accountants & Advisors",
  description:
    "Learn what online bookkeeping is, how it works, what it includes, and when a business may need professional bookkeeping support.",
  canonical: "https://www.hanoveraa.com/resources/bookkeeping/what-is-online-bookkeeping/",
  h1: "What Is Online Bookkeeping?",
  ogTitle: "What Is Online Bookkeeping?",
  ogDescription:
    "A plain-English guide to online bookkeeping, including how it works and what businesses should know.",
  ogImage: "/images/og/bookkeeping-og.jpg",
  robots: {
    index: true,
    follow: true,
  },
}
```

---

# 22. Final Metadata Direction

The Hanover metadata strategy should make each page clear, accurate, and search-friendly.

The metadata should reinforce:

```txt
Nationwide online service availability
Accounting, bookkeeping, tax, payroll, CFO, and advisory expertise
Audience-specific relevance
Local service-area visibility
Secure online workflows
Professional support
Consultation-based conversion
```

Metadata must never invent claims, fake offices, fake reviews, fake guarantees, or fake credentials.

Every page should have metadata that accurately represents the visible page content and supports the larger site architecture.
