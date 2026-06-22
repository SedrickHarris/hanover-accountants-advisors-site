# Services Data Plan

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the service data structure for the Hanover Accountants & Advisors website rebuild.

The services data plan will support:

* Service hub pages
* Service category hub pages
* Individual service pages
* Audience + service pages
* Nationwide + service pages
* Local + service pages
* Industry + service pages
* Related service links
* Metadata generation
* Schema generation
* Sitemap generation
* Navigation
* Internal linking
* CTA logic

The site should be built as a scalable, data-driven Next.js website where all core services are defined in one central data layer.

---

# 1. Service Data File Location

Recommended file:

```txt
src/data/services.ts
```

Optional supporting files:

```txt
src/data/serviceCategories.ts
src/data/serviceGroups.ts
src/data/relatedServices.ts
src/data/serviceMetadata.ts
src/data/serviceFaqs.ts
```

For a clean first build, use:

```txt
src/data/services.ts
src/data/serviceCategories.ts
```

---

# 2. Service Category Structure

The site should organize services into three primary categories:

```txt
Accounting Services
Tax Services
Advisory Services
```

## Service Category URLs

```txt
/services/accounting
/services/tax
/services/advisory
```

## Recommended Category Data

```ts
export const serviceCategories = [
  {
    title: "Accounting Services",
    slug: "accounting",
    path: "/services/accounting",
    description:
      "Online bookkeeping, monthly accounting, client accounting, payroll, reporting, expense management, budgeting, and forecasting services.",
  },
  {
    title: "Tax Services",
    slug: "tax",
    path: "/services/tax",
    description:
      "Tax preparation, tax planning, tax compliance, sales tax returns, year-end tax planning, and online tax filing services.",
  },
  {
    title: "Advisory Services",
    slug: "advisory",
    path: "/services/advisory",
    description:
      "Outsourced CFO, cash flow management, business advisory, strategic planning, financial performance, valuation, succession, exit planning, fundraising, and internal controls support.",
  },
];
```

---

# 3. Service Data Model

Each service should use a consistent object structure.

## Recommended TypeScript Type

```ts
export type ServiceCategory = "accounting" | "tax" | "advisory";

export type ServicePriority = "primary" | "secondary" | "supporting";

export type Service = {
  title: string;
  slug: string;
  path: string;
  category: ServiceCategory;
  priority: ServicePriority;

  shortDescription: string;
  longDescription: string;

  h1: string;
  metaTitle: string;
  metaDescription: string;

  eyebrow?: string;
  directAnswer: string;

  serviceIncludes: string[];
  problemsSolved: string[];
  bestFor: string[];

  relatedServices: string[];
  relatedAudiences: string[];
  relatedIndustries: string[];

  includeInNavigation: boolean;
  includeInServiceHub: boolean;
  includeInAudienceMatrix: boolean;
  includeInNationwideMatrix: boolean;
  includeInLocalMatrix: boolean;
  includeInIndustryMatrix: boolean;

  schemaType: "Service";
};
```

---

# 4. Required Service Fields

Every service should include:

```txt
title
slug
path
category
priority
shortDescription
longDescription
h1
metaTitle
metaDescription
directAnswer
serviceIncludes
problemsSolved
bestFor
relatedServices
relatedAudiences
relatedIndustries
matrix eligibility flags
schema type
```

## Field Purpose

| Field                       | Purpose                                                      |
| --------------------------- | ------------------------------------------------------------ |
| `title`                     | Human-readable service name                                  |
| `slug`                      | URL slug used across all routes                              |
| `path`                      | Main service page path                                       |
| `category`                  | Accounting, tax, or advisory                                 |
| `priority`                  | Helps determine nav, homepage, and internal linking priority |
| `shortDescription`          | Used in cards, grids, and related links                      |
| `longDescription`           | Used for page intro or service overview                      |
| `h1`                        | Main page headline                                           |
| `metaTitle`                 | SEO title tag                                                |
| `metaDescription`           | SEO meta description                                         |
| `directAnswer`              | AEO-style short answer section                               |
| `serviceIncludes`           | Bullets for what the service includes                        |
| `problemsSolved`            | Common issues the service helps address                      |
| `bestFor`                   | Audiences or client situations where the service fits        |
| `relatedServices`           | Slugs of related services                                    |
| `relatedAudiences`          | Slugs of related audience pages                              |
| `relatedIndustries`         | Slugs of related industry pages                              |
| `includeInNavigation`       | Whether to show in dropdown navigation                       |
| `includeInServiceHub`       | Whether to show on `/services`                               |
| `includeInAudienceMatrix`   | Whether service should generate audience + service pages     |
| `includeInNationwideMatrix` | Whether service should generate nationwide + service pages   |
| `includeInLocalMatrix`      | Whether service should generate local + service pages        |
| `includeInIndustryMatrix`   | Whether service should generate industry + service pages     |
| `schemaType`                | Schema type for structured data                              |

---

# 5. Canonical Service Slugs

Use these service slugs consistently across the entire project.

Do not create alternate slugs for the same service unless a redirect is intentionally added.

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

## Tax Service Slugs

```txt
tax-preparation
tax-planning
tax-compliance
sales-tax-returns
year-end-tax-planning
online-tax-filing
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

---

# 6. Full Service Inventory

## Accounting Services

### Online Bookkeeping

```txt
Title: Online Bookkeeping
Slug: online-bookkeeping
Path: /services/online-bookkeeping
Category: accounting
Priority: primary
```

Purpose:

```txt
Supports search intent around online bookkeeping, virtual bookkeeping, remote bookkeeping, and monthly bookkeeping support.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Monthly Accounting Services

```txt
Title: Monthly Accounting Services
Slug: monthly-accounting-services
Path: /services/monthly-accounting-services
Category: accounting
Priority: primary
```

Purpose:

```txt
Supports recurring accounting, monthly books, monthly close, ongoing financial support, and business accounting management intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Client Accounting Services

```txt
Title: Client Accounting Services
Slug: client-accounting-services
Path: /services/client-accounting-services
Category: accounting
Priority: primary
```

Purpose:

```txt
Supports CAS intent, outsourced accounting, recurring business accounting, and client accounting services search queries.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Financial Reporting

```txt
Title: Financial Reporting
Slug: financial-reporting
Path: /services/financial-reporting
Category: accounting
Priority: primary
```

Purpose:

```txt
Supports monthly reports, income statements, balance sheets, cash flow statements, financial analysis, and reporting visibility intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Payroll Services

```txt
Title: Payroll Services
Slug: payroll-services
Path: /services/payroll-services
Category: accounting
Priority: primary
```

Purpose:

```txt
Supports payroll processing, payroll tax filing, employee earnings statements, and small business payroll intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Expense Management

```txt
Title: Expense Management
Slug: expense-management
Path: /services/expense-management
Category: accounting
Priority: secondary
```

Purpose:

```txt
Supports expense tracking, expense reporting, expense analysis, and tax-compliance-related expense organization.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Selective industry pages
```

---

### Budgeting and Forecasting

```txt
Title: Budgeting and Forecasting
Slug: budgeting-forecasting
Path: /services/budgeting-forecasting
Category: accounting
Priority: secondary
```

Purpose:

```txt
Supports budget creation, budget maintenance, cash flow forecasting, financial planning, and variance analysis intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Selective industry pages
```

---

## Tax Services

### Tax Preparation

```txt
Title: Tax Preparation
Slug: tax-preparation
Path: /services/tax-preparation
Category: tax
Priority: primary
```

Purpose:

```txt
Supports online tax preparation, individual tax preparation, business tax preparation, tax filing, secure upload, e-signature, and e-file intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Tax Planning

```txt
Title: Tax Planning
Slug: tax-planning
Path: /services/tax-planning
Category: tax
Priority: primary
```

Purpose:

```txt
Supports proactive tax planning, year-round tax decisions, business owner tax planning, tax strategy, and year-end tax planning intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Tax Compliance

```txt
Title: Tax Compliance
Slug: tax-compliance
Path: /services/tax-compliance
Category: tax
Priority: primary
```

Purpose:

```txt
Supports tax filing obligations, monthly and quarterly filings, compliance workflows, and organized tax reporting support.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Sales Tax Returns

```txt
Title: Sales Tax Returns
Slug: sales-tax-returns
Path: /services/sales-tax-returns
Category: tax
Priority: secondary
```

Purpose:

```txt
Supports sales tax return preparation, filing support, sales tax compliance, and business tax reporting intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Selective industry pages
```

---

### Year-End Tax Planning

```txt
Title: Year-End Tax Planning
Slug: year-end-tax-planning
Path: /services/year-end-tax-planning
Category: tax
Priority: secondary
```

Purpose:

```txt
Supports year-end tax planning, tax readiness, year-end review, business tax planning, and annual financial planning intent.
```

Use in:

```txt
Service page
Nationwide + service pages if approved
Selective audience + service pages
Resource articles
```

---

### Online Tax Filing

```txt
Title: Online Tax Filing
Slug: online-tax-filing
Path: /services/online-tax-filing
Category: tax
Priority: secondary
```

Purpose:

```txt
Supports online filing, e-file, e-signature, secure document upload, virtual tax preparation, and remote tax service intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Resource articles
```

---

## Advisory Services

### Cash Flow Management

```txt
Title: Cash Flow Management
Slug: cash-flow-management
Path: /services/cash-flow-management
Category: advisory
Priority: primary
```

Purpose:

```txt
Supports cash flow analysis, cash flow forecasting, working capital, and cash flow strategy intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Outsourced CFO Services

```txt
Title: Outsourced CFO Services
Slug: outsourced-cfo-services
Path: /services/outsourced-cfo-services
Category: advisory
Priority: primary
```

Purpose:

```txt
Supports virtual CFO, outsourced CFO, CFO advisory, high-level financial guidance, strategic finance, and growing business advisory intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Business Advisory Services

```txt
Title: Business Advisory Services
Slug: business-advisory-services
Path: /services/business-advisory-services
Category: advisory
Priority: primary
```

Purpose:

```txt
Supports business advisory, financial decision support, business planning, growth support, succession support, and strategic guidance intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Strategic Financial Planning

```txt
Title: Strategic Financial Planning
Slug: strategic-financial-planning
Path: /services/strategic-financial-planning
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports long-term planning, business modeling, scenario planning, capital structure, and strategic financial decision-making intent.
```

Use in:

```txt
Service page
Nationwide + service pages if approved
Selective audience + service pages
Selective industry pages
```

---

### Financial Performance Management

```txt
Title: Financial Performance Management
Slug: financial-performance-management
Path: /services/financial-performance-management
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports KPI tracking, profitability analysis, cost control, performance review, and financial risk management intent.
```

Use in:

```txt
Service page
Nationwide + service pages if approved
Selective audience + service pages
Selective industry pages
```

---

### Business Valuation

```txt
Title: Business Valuation
Slug: business-valuation
Path: /services/business-valuation
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports business valuation, ownership transition, sale readiness, succession, financing, and advisory review intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Due Diligence Support

```txt
Title: Due Diligence Support
Slug: due-diligence-support
Path: /services/due-diligence-support
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports transaction review, acquisition support, financial due diligence, documentation review, and business advisory search intent.
```

Use in:

```txt
Service page
Selective audience + service pages
Selective resource pages
Selective industry pages
```

---

### Succession Planning

```txt
Title: Succession Planning
Slug: succession-planning
Path: /services/succession-planning
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports family business succession, ownership transition, business continuity, exit planning, and long-term advisory intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages where relevant
```

---

### Exit Strategy Planning

```txt
Title: Exit Strategy Planning
Slug: exit-strategy-planning
Path: /services/exit-strategy-planning
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports exit strategy, business sale planning, transition planning, succession planning, and owner advisory intent.
```

Use in:

```txt
Service page
Selective audience + service pages
Selective industry pages
Resource articles
```

---

### Fundraising and Investor Relations

```txt
Title: Fundraising and Investor Relations
Slug: fundraising-investor-relations
Path: /services/fundraising-investor-relations
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports investor presentation support, debt fundraising, equity fundraising, capital raise preparation, and investor communication intent.
```

Use in:

```txt
Service page
Audience + service pages
Nationwide + service pages
Local + service pages
Selective industry pages
```

---

### Internal Controls Review

```txt
Title: Internal Controls Review
Slug: internal-controls-review
Path: /services/internal-controls-review
Category: advisory
Priority: secondary
```

Purpose:

```txt
Supports internal controls assessment, process improvement, reporting controls, risk reduction, and financial operations review intent.
```

Use in:

```txt
Service page
Selective audience + service pages
Selective industry pages
Resource articles
```

---

# 7. Service Matrix Eligibility

Not every service must appear in every matrix.

Use data flags to control whether a service appears in audience, nationwide, local, and industry matrix pages.

## Matrix Flag Definitions

```txt
includeInAudienceMatrix
includeInNationwideMatrix
includeInLocalMatrix
includeInIndustryMatrix
```

## Recommended Matrix Eligibility

| Service                            | Audience Matrix | Nationwide Matrix | Local Matrix | Industry Matrix |
| ---------------------------------- | --------------: | ----------------: | -----------: | --------------: |
| Online Bookkeeping                 |             Yes |               Yes |          Yes |             Yes |
| Monthly Accounting Services        |             Yes |               Yes |          Yes |             Yes |
| Client Accounting Services         |             Yes |               Yes |          Yes |             Yes |
| Financial Reporting                |             Yes |               Yes |          Yes |             Yes |
| Payroll Services                   |             Yes |               Yes |          Yes |             Yes |
| Expense Management                 |             Yes |               Yes |          Yes |       Selective |
| Budgeting and Forecasting          |             Yes |               Yes |          Yes |       Selective |
| Tax Preparation                    |             Yes |               Yes |          Yes |             Yes |
| Tax Planning                       |             Yes |               Yes |          Yes |             Yes |
| Tax Compliance                     |             Yes |               Yes |          Yes |             Yes |
| Sales Tax Returns                  |             Yes |               Yes |          Yes |       Selective |
| Year-End Tax Planning              |       Selective |         Selective |    Selective |       Selective |
| Online Tax Filing                  |       Selective |               Yes |    Selective |              No |
| Cash Flow Management               |             Yes |               Yes |          Yes |             Yes |
| Outsourced CFO Services            |             Yes |               Yes |          Yes |             Yes |
| Business Advisory Services         |             Yes |               Yes |          Yes |             Yes |
| Strategic Financial Planning       |       Selective |         Selective |    Selective |       Selective |
| Financial Performance Management   |       Selective |         Selective |    Selective |       Selective |
| Business Valuation                 |             Yes |               Yes |          Yes |       Selective |
| Due Diligence Support              |       Selective |         Selective |    Selective |       Selective |
| Succession Planning                |             Yes |               Yes |          Yes |             Yes |
| Exit Strategy Planning             |       Selective |         Selective |    Selective |       Selective |
| Fundraising and Investor Relations |             Yes |               Yes |          Yes |       Selective |
| Internal Controls Review           |       Selective |         Selective |    Selective |       Selective |

---

# 8. Priority Service Navigation

Not every service should appear in the main dropdown.

## Primary Navigation Services

```txt
Online Bookkeeping
Monthly Accounting Services
Tax Preparation
Tax Planning
Payroll Services
Outsourced CFO Services
Business Advisory Services
```

## Secondary Services

Secondary services should be reachable from:

```txt
Service category hubs
Related service sections
Footer links where appropriate
HTML sitemap
XML sitemap
Resource articles
Audience + service pages
Location + service pages
```

---

# 9. Related Service Mapping

Each service should include related service slugs.

## Example Related Services

### Online Bookkeeping

```txt
monthly-accounting-services
client-accounting-services
financial-reporting
expense-management
tax-preparation
```

### Monthly Accounting Services

```txt
online-bookkeeping
client-accounting-services
financial-reporting
payroll-services
budgeting-forecasting
```

### Client Accounting Services

```txt
monthly-accounting-services
online-bookkeeping
financial-reporting
tax-compliance
outsourced-cfo-services
```

### Financial Reporting

```txt
monthly-accounting-services
client-accounting-services
cash-flow-management
financial-performance-management
outsourced-cfo-services
```

### Payroll Services

```txt
monthly-accounting-services
tax-compliance
sales-tax-returns
client-accounting-services
```

### Tax Preparation

```txt
tax-planning
tax-compliance
online-tax-filing
year-end-tax-planning
online-bookkeeping
```

### Tax Planning

```txt
tax-preparation
tax-compliance
year-end-tax-planning
business-advisory-services
cash-flow-management
```

### Tax Compliance

```txt
tax-preparation
tax-planning
sales-tax-returns
monthly-accounting-services
client-accounting-services
```

### Outsourced CFO Services

```txt
business-advisory-services
cash-flow-management
strategic-financial-planning
financial-performance-management
business-valuation
```

### Business Advisory Services

```txt
outsourced-cfo-services
cash-flow-management
business-valuation
succession-planning
exit-strategy-planning
```

### Cash Flow Management

```txt
financial-reporting
budgeting-forecasting
outsourced-cfo-services
business-advisory-services
financial-performance-management
```

### Business Valuation

```txt
business-advisory-services
succession-planning
exit-strategy-planning
due-diligence-support
outsourced-cfo-services
```

### Succession Planning

```txt
business-valuation
exit-strategy-planning
business-advisory-services
tax-planning
outsourced-cfo-services
```

### Fundraising and Investor Relations

```txt
outsourced-cfo-services
strategic-financial-planning
financial-reporting
business-advisory-services
due-diligence-support
```

### Internal Controls Review

```txt
financial-reporting
financial-performance-management
client-accounting-services
business-advisory-services
outsourced-cfo-services
```

---

# 10. Related Audience Mapping

Each service should connect to relevant audiences.

## Recommended Audience Slugs

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

## Audience Fit by Service

### Strong Fit for Individuals

```txt
tax-preparation
tax-planning
online-tax-filing
```

### Strong Fit for Entrepreneurs

```txt
online-bookkeeping
monthly-accounting-services
financial-reporting
tax-preparation
tax-planning
tax-compliance
expense-management
budgeting-forecasting
cash-flow-management
business-advisory-services
```

### Strong Fit for Startups

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
fundraising-investor-relations
```

### Strong Fit for Small Businesses

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
```

### Strong Fit for Medium-Sized Businesses

```txt
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
tax-preparation
tax-planning
tax-compliance
sales-tax-returns
budgeting-forecasting
cash-flow-management
outsourced-cfo-services
business-advisory-services
business-valuation
succession-planning
internal-controls-review
```

### Strong Fit for Family-Owned Businesses

```txt
online-bookkeeping
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
tax-preparation
tax-planning
tax-compliance
expense-management
budgeting-forecasting
cash-flow-management
outsourced-cfo-services
business-advisory-services
business-valuation
succession-planning
exit-strategy-planning
```

### Strong Fit for Business Owners

```txt
online-bookkeeping
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
tax-preparation
tax-planning
tax-compliance
expense-management
budgeting-forecasting
cash-flow-management
outsourced-cfo-services
business-advisory-services
business-valuation
succession-planning
exit-strategy-planning
```

### Strong Fit for Growing Companies

```txt
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
tax-preparation
tax-planning
tax-compliance
sales-tax-returns
budgeting-forecasting
cash-flow-management
outsourced-cfo-services
business-advisory-services
fundraising-investor-relations
internal-controls-review
```

---

# 11. Related Industry Mapping

Use these industries:

```txt
agriculture
construction
design-firms
food-processing
professional-services
textile-businesses
```

## Strong Industry Service Fits

### Agriculture

```txt
monthly-accounting-services
financial-reporting
tax-planning
tax-compliance
cash-flow-management
business-advisory-services
```

### Construction

```txt
online-bookkeeping
monthly-accounting-services
payroll-services
financial-reporting
tax-planning
cash-flow-management
business-advisory-services
```

### Design Firms

```txt
online-bookkeeping
monthly-accounting-services
tax-preparation
tax-planning
expense-management
business-advisory-services
```

### Food Processing

```txt
monthly-accounting-services
client-accounting-services
financial-reporting
payroll-services
tax-compliance
cash-flow-management
business-advisory-services
```

### Professional Services

```txt
online-bookkeeping
monthly-accounting-services
tax-planning
financial-reporting
outsourced-cfo-services
business-advisory-services
```

### Textile Businesses

```txt
monthly-accounting-services
client-accounting-services
tax-compliance
financial-reporting
cash-flow-management
succession-planning
```

---

# 12. Sample Service Object

Use this as a model for `src/data/services.ts`.

```ts
export const services = [
  {
    title: "Online Bookkeeping",
    slug: "online-bookkeeping",
    path: "/services/online-bookkeeping",
    category: "accounting",
    priority: "primary",

    shortDescription:
      "Secure online bookkeeping support for businesses that need organized records, reconciled accounts, and clearer financial visibility.",
    longDescription:
      "Hanover provides online bookkeeping services to help clients keep financial records organized, current, and easier to understand through secure online workflows and professional support.",

    h1: "Online Bookkeeping Services",
    metaTitle: "Online Bookkeeping Services | Hanover Accountants & Advisors",
    metaDescription:
      "Online bookkeeping services for businesses that need organized records, reconciliations, reporting support, and secure professional accounting help.",

    eyebrow: "Accounting Services",
    directAnswer:
      "Online bookkeeping helps businesses keep transactions, accounts, records, and reports organized through a secure remote accounting workflow.",

    serviceIncludes: [
      "Transaction organization",
      "Bank and credit card reconciliation",
      "Bill and invoice support",
      "General ledger organization",
      "Monthly bookkeeping support",
      "Financial record review",
    ],

    problemsSolved: [
      "Unorganized books",
      "Delayed financial records",
      "Unclear business performance",
      "Disconnected financial information",
      "Difficulty preparing for tax season",
    ],

    bestFor: [
      "Entrepreneurs",
      "Startups",
      "Small businesses",
      "Family-owned businesses",
      "Business owners",
      "Growing companies",
    ],

    relatedServices: [
      "monthly-accounting-services",
      "client-accounting-services",
      "financial-reporting",
      "expense-management",
      "tax-preparation",
    ],

    relatedAudiences: [
      "entrepreneurs",
      "startups",
      "small-businesses",
      "family-owned-businesses",
      "business-owners",
    ],

    relatedIndustries: [
      "construction",
      "design-firms",
      "professional-services",
    ],

    includeInNavigation: true,
    includeInServiceHub: true,
    includeInAudienceMatrix: true,
    includeInNationwideMatrix: true,
    includeInLocalMatrix: true,
    includeInIndustryMatrix: true,

    schemaType: "Service",
  },
];
```

---

# 13. Service Page Template Data Requirements

Each service page should be able to pull from the service data file to generate:

```txt
H1
Eyebrow
Short description
Direct answer
Hero content
Service includes list
Problems solved list
Best-for audience list
Related services
Related audiences
Related industries
FAQs
CTA
Metadata
Schema
Breadcrumbs
```

## Service Page Sections

Every service page should include:

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

---

# 14. Metadata Generation Rules

Every service should include custom metadata.

## Title Tag Pattern

```txt
[Service Name] | Hanover Accountants & Advisors
```

Examples:

```txt
Online Bookkeeping Services | Hanover Accountants & Advisors
Tax Preparation Services | Hanover Accountants & Advisors
Outsourced CFO Services | Hanover Accountants & Advisors
```

## Meta Description Pattern

Meta descriptions should be specific and human-readable.

Good:

```txt
Online bookkeeping services for businesses that need organized records, reconciliations, reporting support, and secure professional accounting help.
```

Avoid:

```txt
Best online bookkeeping services nationwide for accounting tax bookkeeping payroll CFO advisory and more.
```

---

# 15. Schema Generation Rules

Each service page should generate `Service` schema.

## Required Service Schema Inputs

```txt
name
description
provider
areaServed
serviceType
url
```

## Service Schema Area Served

For general service pages:

```txt
United States
```

For local + service pages:

```txt
Specific city or service area
```

## Do Not Add

Do not add:

```txt
Fake reviews
Fake aggregate ratings
Fake prices
Fake guarantees
Fake service hours
Fake office locations
```

---

# 16. Service Data and Sitemap Generation

The service data should be used to generate sitemap entries.

## Include in Sitemap

```txt
/services
/services/accounting
/services/tax
/services/advisory
/services/[service]
```

Each service with `includeInServiceHub: true` should appear in the sitemap and services hub.

---

# 17. Service Data and Internal Linking

The service data should power internal linking across:

```txt
Service pages
Audience pages
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages
Resource articles
FAQ pages
```

## Internal Link Rules

Each service page should link to:

```txt
Parent service category
Related services
Related audiences
Nationwide + service page
Priority local + service pages
Relevant resource articles
Schedule consultation page
```

---

# 18. Service Data and Navigation

Only primary services should appear in dropdown navigation.

## `includeInNavigation: true`

Use for:

```txt
online-bookkeeping
monthly-accounting-services
tax-preparation
tax-planning
payroll-services
outsourced-cfo-services
business-advisory-services
```

## `includeInNavigation: false`

Use for most secondary and supporting services.

These pages should still be discoverable through:

```txt
Service hubs
Related links
Footer
Sitemap
Resources
FAQs
Matrix pages
```

---

# 19. Service Data and Matrix Generation

The service data should power:

```txt
Audience + service page generation
Nationwide + service page generation
Local + service page generation
Optional industry + service page generation
```

## Audience Matrix

Use:

```txt
includeInAudienceMatrix: true
```

## Nationwide Matrix

Use:

```txt
includeInNationwideMatrix: true
```

## Local Matrix

Use:

```txt
includeInLocalMatrix: true
```

## Industry Matrix

Use:

```txt
includeInIndustryMatrix: true
```

Selective services can be excluded from certain matrices to avoid low-value pages.

---

# 20. Service Data Quality Rules

The services data must avoid:

```txt
Duplicate service slugs
Duplicate service paths
Duplicate metadata
Unsupported service claims
Fake guarantees
Fake pricing
Fake credentials
Fake reviews
Fake local office claims
Overlapping service pages with unclear distinctions
```

Each service should have a clear purpose and relationship to the rest of the site.

---

# 21. Initial Services Data Checklist

Before build, confirm:

```txt
All service slugs are final.
All service titles are final.
All services belong to the correct category.
Priority services are marked correctly.
Navigation services are marked correctly.
Audience matrix services are marked correctly.
Nationwide matrix services are marked correctly.
Local matrix services are marked correctly.
Industry matrix services are marked correctly.
Related services are mapped.
Related audiences are mapped.
Related industries are mapped.
Metadata is unique.
Schema inputs are present.
No unsupported claims are included.
```

---

# 22. Final Services Data Direction

The Hanover site should use a central services data layer to keep the build scalable, consistent, and easier to maintain.

The services data should support:

```txt
Service pages
Service category hubs
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages
Resources
FAQs
Metadata
Schema
Sitemap generation
Internal links
Navigation
Conversion CTAs
```

This data plan allows Hanover to build a large, high-quality site without losing structure, consistency, or accuracy.
