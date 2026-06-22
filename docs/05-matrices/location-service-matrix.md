# Location Service Matrix

## Project

Hanover Accountants & Advisors Website Rebuild

> ⚠️ **Editorial note (added during intake):** In the source document, the Smyrna, GA
> block in Section 17 arrived corrupted — it contained malformed slugs
> (`business-pliance`, `cvaluation`) and duplicated lines, and omitted several valid
> services. It has been corrected here to match the canonical 17-service list defined in
> Section 7, consistent with every other city group. No other content was changed.

## Purpose of This Document

This document defines the nationwide, local service-area, and location + service matrix for the Hanover Accountants & Advisors website rebuild.

The matrix supports:

* Nationwide service visibility
* Local service-area visibility
* Local intent SERPs
* SEO
* GEO
* AEO
* Google Business Profile support
* Apple Search and Apple Business Connect alignment
* Bing Webmaster indexing
* Google Search Console indexing
* LLM search visibility
* Featured snippets
* People Also Ask visibility
* Rich snippets
* Customer engagement
* Customer conversion
* Static route generation in Next.js

The site will position Hanover as a nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory firm while keeping all approved local service-area pages.

---

# 1. Service Area Strategy

Hanover should use a service-area architecture, not a simple location-only architecture.

## Primary Structure

```txt
/service-areas
/service-areas/nationwide
/service-areas/nationwide/[service]
/service-areas/[location]
/service-areas/[location]/[service]
```

## Why Use `/service-areas`

Use `/service-areas` because Hanover serves clients nationwide through secure online workflows and also needs local search visibility.

This structure supports:

```txt
Nationwide service intent
Local service intent
Physical office pages, where verified
Remote service-area pages
Google Business Profile alignment
Apple Business Connect alignment
Local search visibility without fake office claims
```

---

# 2. Important Location Accuracy Rule

Do not claim a physical office in a city unless confirmed by the client.

The current site has a Virginia inconsistency that must be clarified before launch.

## Virginia Location Issue

The current site references a Richmond, Virginia office, but the displayed address is in Alexandria, Virginia.

Before final launch, confirm:

```txt
Is Alexandria, VA a physical office?
Is Richmond, VA a physical office?
Is Richmond, VA only a service area?
Is the Richmond language old or incorrect copy?
Which Virginia address should be used publicly?
Which address should be used for LocalBusiness schema?
Which location should connect to Google Business Profile?
Which location should connect to Apple Business Connect?
```

## Safe Language for Unverified Physical Offices

Use service-area language:

```txt
Hanover serves clients in [city] through secure online accounting, tax, bookkeeping, payroll, and advisory services.
```

Do not write:

```txt
Visit our [city] office.
```

Unless the office is verified.

---

# 3. Service Area Hub

## Hub URL

```txt
/service-areas
```

## Page Purpose

The service areas hub should explain that Hanover serves clients nationwide and supports clients in specific Georgia and Virginia markets.

The page should link to:

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

---

# 4. Nationwide Service Area Page

## Nationwide Hub URL

```txt
/service-areas/nationwide
```

## Page Purpose

The nationwide service-area page should explain how Hanover provides accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services to clients across the United States through secure online workflows.

## Suggested H1

```txt
Nationwide Online Accounting, Tax, Bookkeeping & Advisory Services
```

## Suggested Positioning

```txt
Hanover provides online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services nationwide through secure document workflows, professional support, and consultation-based service planning.
```

---

# 5. Nationwide + Service Matrix

## Slug Pattern

```txt
/service-areas/nationwide/[service]
```

## Nationwide + Service Pages

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
/service-areas/nationwide/expense-management
/service-areas/nationwide/budgeting-forecasting
/service-areas/nationwide/cash-flow-management
/service-areas/nationwide/outsourced-cfo-services
/service-areas/nationwide/business-advisory-services
/service-areas/nationwide/business-valuation
/service-areas/nationwide/succession-planning
/service-areas/nationwide/fundraising-investor-relations
```

## Nationwide + Service Page Count

```txt
17 nationwide + service pages
```

---

# 6. Local Service Areas

## Georgia Local Service Areas

```txt
atlanta-ga
vinings-ga
sandy-springs-ga
marietta-ga
smyrna-ga
buckhead-atlanta-ga
```

## Virginia Local Service Areas

```txt
alexandria-va
arlington-va
fairfax-va
richmond-va
```

## Full Local Service Area Pages

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

## Local Service Area Page Count

```txt
10 local service-area pages
```

---

# 7. Local Services Used in the Matrix

The local + service matrix will use these services:

```txt
online-bookkeeping
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
tax-preparation
tax-planning
tax-compliance
sales-tax-returns
expense-management
budgeting-forecasting
cash-flow-management
outsourced-cfo-services
business-advisory-services
business-valuation
succession-planning
fundraising-investor-relations
```

## Local Matrix Count

```txt
10 local service areas x 17 services = 170 local + service pages
```

---

# 8. Location Data File

Recommended file:

```txt
src/data/serviceAreas.ts
```

Recommended supporting file:

```txt
src/data/locationServiceMatrix.ts
```

---

# 9. Service Area Data Model

## Recommended TypeScript Type

```ts
export type ServiceAreaType =
  | "nationwide"
  | "verified-office"
  | "primary-market"
  | "service-area";

export type ServiceArea = {
  title: string;
  slug: string;
  path: string;
  state?: string;
  stateAbbreviation?: string;
  region?: string;
  type: ServiceAreaType;
  isPhysicalOffice: boolean;
  physicalOfficeStatus: "verified" | "needs-confirmation" | "not-a-physical-office";
  shortDescription: string;
  longDescription: string;
  h1: string;
  metaTitle: string;
  metaDescription: string;
  relatedServiceAreas: string[];
  priorityServices: string[];
  includeInNavigation: boolean;
  includeInSitemap: boolean;
  includeInLocalMatrix: boolean;
};
```

---

# 10. Location + Service Data Model

## Recommended TypeScript Type

```ts
export type LocationServicePage = {
  locationSlug: string;
  serviceSlug: string;
  path: string;
  title: string;
  h1: string;
  metaTitle: string;
  metaDescription: string;
  directAnswer: string;
  localIntent: string;
  serviceDeliveryModel: "online" | "office-and-online" | "service-area-online";
  isPhysicalOfficePage: boolean;
  schemaMode: "local-business" | "service-area";
  relatedLocalServices: string[];
  relatedServiceAreas: string[];
  relatedResources: string[];
  includeInSitemap: boolean;
  includeInIndex: boolean;
};
```

---

# 11. Recommended Service Area Objects

## Nationwide

```ts
{
  title: "Nationwide",
  slug: "nationwide",
  path: "/service-areas/nationwide",
  type: "nationwide",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Nationwide online accounting, bookkeeping, tax, payroll, outsourced CFO, and advisory services.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: false,
}
```

## Atlanta, GA

```ts
{
  title: "Atlanta, GA",
  slug: "atlanta-ga",
  path: "/service-areas/atlanta-ga",
  state: "Georgia",
  stateAbbreviation: "GA",
  region: "Atlanta Metro",
  type: "verified-office",
  isPhysicalOffice: true,
  physicalOfficeStatus: "verified",
  shortDescription:
    "Accounting, tax, bookkeeping, payroll, and advisory services for clients in Atlanta, GA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Vinings, GA

```ts
{
  title: "Vinings, GA",
  slug: "vinings-ga",
  path: "/service-areas/vinings-ga",
  state: "Georgia",
  stateAbbreviation: "GA",
  region: "Atlanta Metro",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Vinings, GA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Sandy Springs, GA

```ts
{
  title: "Sandy Springs, GA",
  slug: "sandy-springs-ga",
  path: "/service-areas/sandy-springs-ga",
  state: "Georgia",
  stateAbbreviation: "GA",
  region: "Atlanta Metro",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Sandy Springs, GA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Marietta, GA

```ts
{
  title: "Marietta, GA",
  slug: "marietta-ga",
  path: "/service-areas/marietta-ga",
  state: "Georgia",
  stateAbbreviation: "GA",
  region: "Atlanta Metro",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Marietta, GA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Smyrna, GA

```ts
{
  title: "Smyrna, GA",
  slug: "smyrna-ga",
  path: "/service-areas/smyrna-ga",
  state: "Georgia",
  stateAbbreviation: "GA",
  region: "Atlanta Metro",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Smyrna, GA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Buckhead Atlanta, GA

```ts
{
  title: "Buckhead Atlanta, GA",
  slug: "buckhead-atlanta-ga",
  path: "/service-areas/buckhead-atlanta-ga",
  state: "Georgia",
  stateAbbreviation: "GA",
  region: "Atlanta Metro",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Buckhead Atlanta, GA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Alexandria, VA

```ts
{
  title: "Alexandria, VA",
  slug: "alexandria-va",
  path: "/service-areas/alexandria-va",
  state: "Virginia",
  stateAbbreviation: "VA",
  region: "Northern Virginia",
  type: "primary-market",
  isPhysicalOffice: true,
  physicalOfficeStatus: "needs-confirmation",
  shortDescription:
    "Accounting, tax, bookkeeping, payroll, and advisory services for clients in Alexandria, VA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Arlington, VA

```ts
{
  title: "Arlington, VA",
  slug: "arlington-va",
  path: "/service-areas/arlington-va",
  state: "Virginia",
  stateAbbreviation: "VA",
  region: "Northern Virginia",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Arlington, VA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Fairfax, VA

```ts
{
  title: "Fairfax, VA",
  slug: "fairfax-va",
  path: "/service-areas/fairfax-va",
  state: "Virginia",
  stateAbbreviation: "VA",
  region: "Northern Virginia",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "not-a-physical-office",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Fairfax, VA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

## Richmond, VA

```ts
{
  title: "Richmond, VA",
  slug: "richmond-va",
  path: "/service-areas/richmond-va",
  state: "Virginia",
  stateAbbreviation: "VA",
  region: "Virginia",
  type: "service-area",
  isPhysicalOffice: false,
  physicalOfficeStatus: "needs-confirmation",
  shortDescription:
    "Online accounting, tax, bookkeeping, payroll, and advisory services for clients in Richmond, VA.",
  includeInNavigation: true,
  includeInSitemap: true,
  includeInLocalMatrix: true,
}
```

---

# 12. Location + Service Metadata Patterns

Each local + service page must have unique metadata.

## Title Tag Pattern

```txt
[Service] in [City, State] | Hanover Accountants & Advisors
```

Examples:

```txt
Tax Preparation in Atlanta, GA | Hanover Accountants & Advisors
Online Bookkeeping in Alexandria, VA | Hanover Accountants & Advisors
Outsourced CFO Services in Marietta, GA | Hanover Accountants & Advisors
```

## Meta Description Pattern

```txt
Hanover provides [service] for clients in [city, state] through secure online workflows and professional support. Schedule a consultation for accounting, tax, payroll, or advisory help.
```

## H1 Pattern

```txt
[Service] in [City, State]
```

Examples:

```txt
Tax Preparation in Atlanta, GA
Online Bookkeeping in Alexandria, VA
Payroll Services in Sandy Springs, GA
```

## Direct Answer Pattern

```txt
Hanover provides [service] for clients in [city, state] through secure online workflows, professional support, and a consultation-based service process.
```

---

# 13. Location + Service Page Template

Every local + service page should include:

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
Related parent service page
Nearby service areas
FAQs
Final CTA
Schema
```

---

# 14. Local Service-Area Page Template

Every local service-area page should include:

```txt
Hero
Local market overview
How Hanover serves clients in this area
Office or service-area distinction
Services available in this market
Who Hanover helps locally
Secure online workflow
Nearby service areas
Related local service pages
FAQs
Final CTA
Schema
```

---

# 15. Schema Rules

## Verified Physical Office Pages

Only use `LocalBusiness` or `ProfessionalService` schema with address if the physical office is verified.

Use for:

```txt
/service-areas/atlanta-ga
```

Potentially use for Alexandria only after confirmation:

```txt
/service-areas/alexandria-va
```

## Service Area Pages Without Physical Offices

Use:

```txt
Service
AreaServed
FAQPage
BreadcrumbList
```

Do not use fake LocalBusiness schema for:

```txt
/service-areas/vinings-ga
/service-areas/sandy-springs-ga
/service-areas/marietta-ga
/service-areas/smyrna-ga
/service-areas/buckhead-atlanta-ga
/service-areas/arlington-va
/service-areas/fairfax-va
/service-areas/richmond-va
```

Unless a physical office is confirmed.

## Local + Service Pages

Use:

```txt
Service
AreaServed
FAQPage
BreadcrumbList
```

If the page represents a verified physical office and service, it may also reference the verified office organization data carefully.

## Do Not Add

Do not add:

```txt
Fake addresses
Fake business hours
Fake coordinates
Fake office photos
Fake reviews
Fake aggregate ratings
Fake prices
Fake guarantees
```

---

# 16. Internal Linking Rules

## Local Service-Area Pages Should Link To

```txt
Local + service pages for that market
Nearby service-area pages
Nationwide service-area page
Core service pages
Who We Help pages
Schedule consultation page
```

## Local + Service Pages Should Link To

```txt
Parent local service-area page
Core service page
Nationwide + service page
Related local + service pages
Nearby service-area pages
Relevant resources
FAQ category page
Schedule consultation page
```

## Example for `/service-areas/atlanta-ga/tax-preparation`

Link to:

```txt
/service-areas/atlanta-ga
/services/tax-preparation
/service-areas/nationwide/tax-preparation
/service-areas/atlanta-ga/tax-planning
/service-areas/atlanta-ga/tax-compliance
/service-areas/atlanta-ga/online-bookkeeping
/service-areas/sandy-springs-ga/tax-preparation
/service-areas/marietta-ga/tax-preparation
/resources/tax-preparation/online-tax-preparation-checklist
/faqs/tax-preparation
/schedule-consultation
```

---

# 17. Local Matrix Page Groups

## Atlanta, GA + Service Pages

```txt
/service-areas/atlanta-ga/online-bookkeeping
/service-areas/atlanta-ga/monthly-accounting-services
/service-areas/atlanta-ga/client-accounting-services
/service-areas/atlanta-ga/financial-reporting
/service-areas/atlanta-ga/payroll-services
/service-areas/atlanta-ga/tax-preparation
/service-areas/atlanta-ga/tax-planning
/service-areas/atlanta-ga/tax-compliance
/service-areas/atlanta-ga/sales-tax-returns
/service-areas/atlanta-ga/expense-management
/service-areas/atlanta-ga/budgeting-forecasting
/service-areas/atlanta-ga/cash-flow-management
/service-areas/atlanta-ga/outsourced-cfo-services
/service-areas/atlanta-ga/business-advisory-services
/service-areas/atlanta-ga/business-valuation
/service-areas/atlanta-ga/succession-planning
/service-areas/atlanta-ga/fundraising-investor-relations
```

## Vinings, GA + Service Pages

```txt
/service-areas/vinings-ga/online-bookkeeping
/service-areas/vinings-ga/monthly-accounting-services
/service-areas/vinings-ga/client-accounting-services
/service-areas/vinings-ga/financial-reporting
/service-areas/vinings-ga/payroll-services
/service-areas/vinings-ga/tax-preparation
/service-areas/vinings-ga/tax-planning
/service-areas/vinings-ga/tax-compliance
/service-areas/vinings-ga/sales-tax-returns
/service-areas/vinings-ga/expense-management
/service-areas/vinings-ga/budgeting-forecasting
/service-areas/vinings-ga/cash-flow-management
/service-areas/vinings-ga/outsourced-cfo-services
/service-areas/vinings-ga/business-advisory-services
/service-areas/vinings-ga/business-valuation
/service-areas/vinings-ga/succession-planning
/service-areas/vinings-ga/fundraising-investor-relations
```

## Sandy Springs, GA + Service Pages

```txt
/service-areas/sandy-springs-ga/online-bookkeeping
/service-areas/sandy-springs-ga/monthly-accounting-services
/service-areas/sandy-springs-ga/client-accounting-services
/service-areas/sandy-springs-ga/financial-reporting
/service-areas/sandy-springs-ga/payroll-services
/service-areas/sandy-springs-ga/tax-preparation
/service-areas/sandy-springs-ga/tax-planning
/service-areas/sandy-springs-ga/tax-compliance
/service-areas/sandy-springs-ga/sales-tax-returns
/service-areas/sandy-springs-ga/expense-management
/service-areas/sandy-springs-ga/budgeting-forecasting
/service-areas/sandy-springs-ga/cash-flow-management
/service-areas/sandy-springs-ga/outsourced-cfo-services
/service-areas/sandy-springs-ga/business-advisory-services
/service-areas/sandy-springs-ga/business-valuation
/service-areas/sandy-springs-ga/succession-planning
/service-areas/sandy-springs-ga/fundraising-investor-relations
```

## Marietta, GA + Service Pages

```txt
/service-areas/marietta-ga/online-bookkeeping
/service-areas/marietta-ga/monthly-accounting-services
/service-areas/marietta-ga/client-accounting-services
/service-areas/marietta-ga/financial-reporting
/service-areas/marietta-ga/payroll-services
/service-areas/marietta-ga/tax-preparation
/service-areas/marietta-ga/tax-planning
/service-areas/marietta-ga/tax-compliance
/service-areas/marietta-ga/sales-tax-returns
/service-areas/marietta-ga/expense-management
/service-areas/marietta-ga/budgeting-forecasting
/service-areas/marietta-ga/cash-flow-management
/service-areas/marietta-ga/outsourced-cfo-services
/service-areas/marietta-ga/business-advisory-services
/service-areas/marietta-ga/business-valuation
/service-areas/marietta-ga/succession-planning
/service-areas/marietta-ga/fundraising-investor-relations
```

## Smyrna, GA + Service Pages

> Corrected to the canonical 17-service list (see editorial note at top).

```txt
/service-areas/smyrna-ga/online-bookkeeping
/service-areas/smyrna-ga/monthly-accounting-services
/service-areas/smyrna-ga/client-accounting-services
/service-areas/smyrna-ga/financial-reporting
/service-areas/smyrna-ga/payroll-services
/service-areas/smyrna-ga/tax-preparation
/service-areas/smyrna-ga/tax-planning
/service-areas/smyrna-ga/tax-compliance
/service-areas/smyrna-ga/sales-tax-returns
/service-areas/smyrna-ga/expense-management
/service-areas/smyrna-ga/budgeting-forecasting
/service-areas/smyrna-ga/cash-flow-management
/service-areas/smyrna-ga/outsourced-cfo-services
/service-areas/smyrna-ga/business-advisory-services
/service-areas/smyrna-ga/business-valuation
/service-areas/smyrna-ga/succession-planning
/service-areas/smyrna-ga/fundraising-investor-relations
```

## Buckhead Atlanta, GA + Service Pages

```txt
/service-areas/buckhead-atlanta-ga/online-bookkeeping
/service-areas/buckhead-atlanta-ga/monthly-accounting-services
/service-areas/buckhead-atlanta-ga/client-accounting-services
/service-areas/buckhead-atlanta-ga/financial-reporting
/service-areas/buckhead-atlanta-ga/payroll-services
/service-areas/buckhead-atlanta-ga/tax-preparation
/service-areas/buckhead-atlanta-ga/tax-planning
/service-areas/buckhead-atlanta-ga/tax-compliance
/service-areas/buckhead-atlanta-ga/sales-tax-returns
/service-areas/buckhead-atlanta-ga/expense-management
/service-areas/buckhead-atlanta-ga/budgeting-forecasting
/service-areas/buckhead-atlanta-ga/cash-flow-management
/service-areas/buckhead-atlanta-ga/outsourced-cfo-services
/service-areas/buckhead-atlanta-ga/business-advisory-services
/service-areas/buckhead-atlanta-ga/business-valuation
/service-areas/buckhead-atlanta-ga/succession-planning
/service-areas/buckhead-atlanta-ga/fundraising-investor-relations
```

## Alexandria, VA + Service Pages

```txt
/service-areas/alexandria-va/online-bookkeeping
/service-areas/alexandria-va/monthly-accounting-services
/service-areas/alexandria-va/client-accounting-services
/service-areas/alexandria-va/financial-reporting
/service-areas/alexandria-va/payroll-services
/service-areas/alexandria-va/tax-preparation
/service-areas/alexandria-va/tax-planning
/service-areas/alexandria-va/tax-compliance
/service-areas/alexandria-va/sales-tax-returns
/service-areas/alexandria-va/expense-management
/service-areas/alexandria-va/budgeting-forecasting
/service-areas/alexandria-va/cash-flow-management
/service-areas/alexandria-va/outsourced-cfo-services
/service-areas/alexandria-va/business-advisory-services
/service-areas/alexandria-va/business-valuation
/service-areas/alexandria-va/succession-planning
/service-areas/alexandria-va/fundraising-investor-relations
```

## Arlington, VA + Service Pages

```txt
/service-areas/arlington-va/online-bookkeeping
/service-areas/arlington-va/monthly-accounting-services
/service-areas/arlington-va/client-accounting-services
/service-areas/arlington-va/financial-reporting
/service-areas/arlington-va/payroll-services
/service-areas/arlington-va/tax-preparation
/service-areas/arlington-va/tax-planning
/service-areas/arlington-va/tax-compliance
/service-areas/arlington-va/sales-tax-returns
/service-areas/arlington-va/expense-management
/service-areas/arlington-va/budgeting-forecasting
/service-areas/arlington-va/cash-flow-management
/service-areas/arlington-va/outsourced-cfo-services
/service-areas/arlington-va/business-advisory-services
/service-areas/arlington-va/business-valuation
/service-areas/arlington-va/succession-planning
/service-areas/arlington-va/fundraising-investor-relations
```

## Fairfax, VA + Service Pages

```txt
/service-areas/fairfax-va/online-bookkeeping
/service-areas/fairfax-va/monthly-accounting-services
/service-areas/fairfax-va/client-accounting-services
/service-areas/fairfax-va/financial-reporting
/service-areas/fairfax-va/payroll-services
/service-areas/fairfax-va/tax-preparation
/service-areas/fairfax-va/tax-planning
/service-areas/fairfax-va/tax-compliance
/service-areas/fairfax-va/sales-tax-returns
/service-areas/fairfax-va/expense-management
/service-areas/fairfax-va/budgeting-forecasting
/service-areas/fairfax-va/cash-flow-management
/service-areas/fairfax-va/outsourced-cfo-services
/service-areas/fairfax-va/business-advisory-services
/service-areas/fairfax-va/business-valuation
/service-areas/fairfax-va/succession-planning
/service-areas/fairfax-va/fundraising-investor-relations
```

## Richmond, VA + Service Pages

```txt
/service-areas/richmond-va/online-bookkeeping
/service-areas/richmond-va/monthly-accounting-services
/service-areas/richmond-va/client-accounting-services
/service-areas/richmond-va/financial-reporting
/service-areas/richmond-va/payroll-services
/service-areas/richmond-va/tax-preparation
/service-areas/richmond-va/tax-planning
/service-areas/richmond-va/tax-compliance
/service-areas/richmond-va/sales-tax-returns
/service-areas/richmond-va/expense-management
/service-areas/richmond-va/budgeting-forecasting
/service-areas/richmond-va/cash-flow-management
/service-areas/richmond-va/outsourced-cfo-services
/service-areas/richmond-va/business-advisory-services
/service-areas/richmond-va/business-valuation
/service-areas/richmond-va/succession-planning
/service-areas/richmond-va/fundraising-investor-relations
```

---

# 18. Recommended Dynamic Routes

Use these routes:

```txt
app/service-areas/page.tsx
app/service-areas/nationwide/page.tsx
app/service-areas/nationwide/[service]/page.tsx
app/service-areas/[location]/page.tsx
app/service-areas/[location]/[service]/page.tsx
```

Use `generateStaticParams` from:

```txt
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
src/data/services.ts
```

The route should validate:

```txt
Location exists
Service exists
Location + service pair is approved
Page is marked includeInIndex
Page has metadata
Page has schema inputs
Page has internal links
```

---

# 19. Recommended Matrix Data Structure

```ts
export const locationServiceMatrix = [
  {
    locationSlug: "atlanta-ga",
    serviceSlug: "tax-preparation",
    path: "/service-areas/atlanta-ga/tax-preparation",
    title: "Tax Preparation in Atlanta, GA",
    h1: "Tax Preparation in Atlanta, GA",
    metaTitle: "Tax Preparation in Atlanta, GA | Hanover Accountants & Advisors",
    metaDescription:
      "Hanover provides tax preparation for clients in Atlanta, GA through secure online workflows and professional support. Schedule a consultation for tax help.",
    directAnswer:
      "Hanover provides tax preparation for clients in Atlanta, GA through secure online workflows, professional support, and a consultation-based service process.",
    localIntent: "tax preparation in Atlanta GA",
    serviceDeliveryModel: "office-and-online",
    isPhysicalOfficePage: true,
    schemaMode: "local-business",
    relatedLocalServices: [
      "tax-planning",
      "tax-compliance",
      "online-bookkeeping",
    ],
    relatedServiceAreas: [
      "vinings-ga",
      "sandy-springs-ga",
      "marietta-ga",
    ],
    relatedResources: [
      "online-tax-preparation-checklist",
      "what-to-expect-from-a-tax-preparation-review",
    ],
    includeInSitemap: true,
    includeInIndex: true,
  },
];
```

---

# 20. QA Checklist

Before publishing the location matrix, verify:

```txt
Every location slug exists in serviceAreas.ts.
Every service slug exists in services.ts.
Every local + service page route generates correctly.
Every page has a unique H1.
Every page has a unique title tag.
Every page has a unique meta description.
Every page has a direct answer section.
Every page has unique local content.
Every page has relevant FAQs.
Every page links to the parent service-area page.
Every page links to the core service page.
Every page links to the nationwide + service page.
Every page links to the consultation page.
Every page has breadcrumb schema.
Every page has appropriate service schema.
Only verified office pages use LocalBusiness schema.
No page contains fake office claims.
No page contains fake reviews.
No page contains fake pricing.
No page contains fake guarantees.
Every indexable page appears in sitemap.xml.
```

---

# 21. Final Location Matrix Direction

The location service matrix gives Hanover a strong local search structure while preserving nationwide positioning.

The final location architecture includes:

```txt
1 service areas hub
1 nationwide service-area page
17 nationwide + service pages
10 local service-area pages
170 local + service pages
```

Total service-area architecture pages:

```txt
1 + 1 + 17 + 10 + 170 = 199 pages
```

The local pages are approved for the build because they will be individually written with unique, useful, location-specific content.

The final structure should support national visibility, local visibility, AEO, GEO, LLM search, rich snippets, service-area clarity, and customer conversion without relying on thin content or fake local office claims.
