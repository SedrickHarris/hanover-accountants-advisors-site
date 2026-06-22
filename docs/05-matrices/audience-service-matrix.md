# Audience Service Matrix

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the audience + service matrix for the Hanover Accountants & Advisors website rebuild.

The audience + service matrix supports high-intent search queries where a visitor is looking for a specific accounting, tax, bookkeeping, payroll, or advisory service for a specific type of client.

The matrix will support:

* SEO
* GEO
* AEO
* Audience-specific search intent
* LLM search visibility
* Featured snippets
* People Also Ask
* Rich snippets
* Customer engagement
* Customer conversion
* Internal linking
* Sitemap generation
* Static route generation in Next.js

---

# 1. Matrix Strategy Summary

The site will include individual audience pages and audience + service pages.

## Audience Hub

```txt
/who-we-help
```

## Audience Page Pattern

```txt
/who-we-help/[audience]
```

## Audience + Service Page Pattern

```txt
/who-we-help/[audience]/[service]
```

## Example Pages

```txt
/who-we-help/startups/online-bookkeeping
/who-we-help/small-businesses/tax-preparation
/who-we-help/family-owned-businesses/outsourced-cfo-services
/who-we-help/business-owners/tax-planning
/who-we-help/growing-companies/payroll-services
```

---

# 2. Core Audiences

The rebuild will include the following core audiences:

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

---

# 3. Core Audience Data Model

Recommended file:

```txt
src/data/audiences.ts
```

Recommended supporting matrix file:

```txt
src/data/audienceServiceMatrix.ts
```

## Recommended Audience Type

```ts
export type Audience = {
  title: string;
  slug: string;
  path: string;
  shortDescription: string;
  longDescription: string;
  h1: string;
  metaTitle: string;
  metaDescription: string;
  primaryServices: string[];
  secondaryServices: string[];
  relatedAudiences: string[];
  relatedIndustries: string[];
  includeInNavigation: boolean;
  includeInSitemap: boolean;
};
```

## Recommended Audience + Service Type

```ts
export type AudienceServicePage = {
  audienceSlug: string;
  serviceSlug: string;
  path: string;
  title: string;
  h1: string;
  metaTitle: string;
  metaDescription: string;
  directAnswer: string;
  primaryIntent: string;
  relatedServices: string[];
  relatedResources: string[];
  includeInSitemap: boolean;
  includeInIndex: boolean;
};
```

---

# 4. Audience Page Goals

Each audience page should answer:

```txt
Does Hanover work with this type of client?
What financial, accounting, tax, payroll, or advisory challenges does this audience face?
Which Hanover services are most relevant?
How does Hanover's secure online workflow support this audience?
What should the visitor do next?
```

Each audience + service page should answer:

```txt
How does this service apply to this audience?
Why does this audience need this service?
What does Hanover provide?
What problems does this service help solve?
How does the secure online workflow work?
Which related services should the visitor consider?
How can the visitor schedule a consultation?
```

---

# 5. Audience + Service Page Template

Each audience + service page should include:

```txt
Hero
Direct answer
Audience-specific pain points
Why this service matters for this audience
What Hanover provides
What is included
Secure online workflow
Common issues solved
Related services
Related audience links
Related resources
FAQs
Final CTA
Schema
```

## Required CTA

Every audience + service page should include a primary CTA:

```txt
Schedule a Consultation
```

Secondary CTAs can include:

```txt
Explore Services
View Nationwide Services
See Who We Help
Learn How Online Accounting Works
```

---

# 6. Audience + Service Matrix Overview

## Page Count Summary

```txt
Individuals: 3
Entrepreneurs: 10
Startups: 15
Small businesses: 14
Medium-sized businesses: 15
Family-owned businesses: 16
Business owners: 16
Growing companies: 14

Total audience + service pages: 103
```

---

# 7. Individuals + Service Pages

Individuals have a narrower service fit than business audiences. Their pages should focus on personal tax preparation, tax planning, and online tax filing.

## Page List

```txt
/who-we-help/individuals/tax-preparation
/who-we-help/individuals/tax-planning
/who-we-help/individuals/online-tax-filing
```

## Page Intent

| Page                                         | Search Intent                     |
| -------------------------------------------- | --------------------------------- |
| `/who-we-help/individuals/tax-preparation`   | Tax preparation for individuals   |
| `/who-we-help/individuals/tax-planning`      | Tax planning for individuals      |
| `/who-we-help/individuals/online-tax-filing` | Online tax filing for individuals |

## Suggested Positioning

```txt
Hanover helps individuals prepare, organize, review, and file taxes through a secure online workflow with professional support.
```

## Related Services

```txt
tax-preparation
tax-planning
online-tax-filing
year-end-tax-planning
```

---

# 8. Entrepreneurs + Service Pages

Entrepreneur pages should focus on getting organized, understanding financial activity, planning for taxes, and making better business decisions.

## Page List

```txt
/who-we-help/entrepreneurs/online-bookkeeping
/who-we-help/entrepreneurs/monthly-accounting-services
/who-we-help/entrepreneurs/financial-reporting
/who-we-help/entrepreneurs/tax-preparation
/who-we-help/entrepreneurs/tax-planning
/who-we-help/entrepreneurs/tax-compliance
/who-we-help/entrepreneurs/expense-management
/who-we-help/entrepreneurs/budgeting-forecasting
/who-we-help/entrepreneurs/cash-flow-management
/who-we-help/entrepreneurs/business-advisory-services
```

## Page Intent

| Page                                                     | Search Intent                                 |
| -------------------------------------------------------- | --------------------------------------------- |
| `/who-we-help/entrepreneurs/online-bookkeeping`          | Online bookkeeping for entrepreneurs          |
| `/who-we-help/entrepreneurs/monthly-accounting-services` | Monthly accounting services for entrepreneurs |
| `/who-we-help/entrepreneurs/financial-reporting`         | Financial reporting for entrepreneurs         |
| `/who-we-help/entrepreneurs/tax-preparation`             | Tax preparation for entrepreneurs             |
| `/who-we-help/entrepreneurs/tax-planning`                | Tax planning for entrepreneurs                |
| `/who-we-help/entrepreneurs/tax-compliance`              | Tax compliance for entrepreneurs              |
| `/who-we-help/entrepreneurs/expense-management`          | Expense management for entrepreneurs          |
| `/who-we-help/entrepreneurs/budgeting-forecasting`       | Budgeting and forecasting for entrepreneurs   |
| `/who-we-help/entrepreneurs/cash-flow-management`        | Cash flow management for entrepreneurs        |
| `/who-we-help/entrepreneurs/business-advisory-services`  | Business advisory services for entrepreneurs  |

## Suggested Positioning

```txt
Hanover helps entrepreneurs organize financial records, prepare for taxes, understand cash flow, and make informed business decisions through secure online accounting and advisory support.
```

## Related Services

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

---

# 9. Startups + Service Pages

Startup pages should focus on early financial systems, scalable accounting, payroll setup, tax readiness, advisory support, and fundraising preparation.

## Page List

```txt
/who-we-help/startups/online-bookkeeping
/who-we-help/startups/monthly-accounting-services
/who-we-help/startups/client-accounting-services
/who-we-help/startups/financial-reporting
/who-we-help/startups/payroll-services
/who-we-help/startups/tax-preparation
/who-we-help/startups/tax-planning
/who-we-help/startups/tax-compliance
/who-we-help/startups/sales-tax-returns
/who-we-help/startups/expense-management
/who-we-help/startups/budgeting-forecasting
/who-we-help/startups/cash-flow-management
/who-we-help/startups/outsourced-cfo-services
/who-we-help/startups/business-advisory-services
/who-we-help/startups/fundraising-investor-relations
```

## Page Intent

| Page                                                   | Search Intent                                           |
| ------------------------------------------------------ | ------------------------------------------------------- |
| `/who-we-help/startups/online-bookkeeping`             | Online bookkeeping for startups                         |
| `/who-we-help/startups/monthly-accounting-services`    | Monthly accounting services for startups                |
| `/who-we-help/startups/client-accounting-services`     | Client accounting services for startups                 |
| `/who-we-help/startups/financial-reporting`            | Financial reporting for startups                        |
| `/who-we-help/startups/payroll-services`               | Payroll services for startups                           |
| `/who-we-help/startups/tax-preparation`                | Tax preparation for startups                            |
| `/who-we-help/startups/tax-planning`                   | Tax planning for startups                               |
| `/who-we-help/startups/tax-compliance`                 | Tax compliance for startups                             |
| `/who-we-help/startups/sales-tax-returns`              | Sales tax return support for startups                   |
| `/who-we-help/startups/expense-management`             | Expense management for startups                         |
| `/who-we-help/startups/budgeting-forecasting`          | Budgeting and forecasting for startups                  |
| `/who-we-help/startups/cash-flow-management`           | Cash flow management for startups                       |
| `/who-we-help/startups/outsourced-cfo-services`        | Outsourced CFO services for startups                    |
| `/who-we-help/startups/business-advisory-services`     | Business advisory services for startups                 |
| `/who-we-help/startups/fundraising-investor-relations` | Fundraising and investor relations support for startups |

## Suggested Positioning

```txt
Hanover helps startups build stronger accounting, tax, payroll, reporting, and advisory foundations through secure online services that can scale as the business grows.
```

## Related Services

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

---

# 10. Small Businesses + Service Pages

Small business pages should focus on organized books, monthly accounting, tax preparation, payroll, compliance, cash flow, and owner decision support.

## Page List

```txt
/who-we-help/small-businesses/online-bookkeeping
/who-we-help/small-businesses/monthly-accounting-services
/who-we-help/small-businesses/client-accounting-services
/who-we-help/small-businesses/financial-reporting
/who-we-help/small-businesses/payroll-services
/who-we-help/small-businesses/tax-preparation
/who-we-help/small-businesses/tax-planning
/who-we-help/small-businesses/tax-compliance
/who-we-help/small-businesses/sales-tax-returns
/who-we-help/small-businesses/expense-management
/who-we-help/small-businesses/budgeting-forecasting
/who-we-help/small-businesses/cash-flow-management
/who-we-help/small-businesses/outsourced-cfo-services
/who-we-help/small-businesses/business-advisory-services
```

## Page Intent

| Page                                                        | Search Intent                                    |
| ----------------------------------------------------------- | ------------------------------------------------ |
| `/who-we-help/small-businesses/online-bookkeeping`          | Online bookkeeping for small businesses          |
| `/who-we-help/small-businesses/monthly-accounting-services` | Monthly accounting services for small businesses |
| `/who-we-help/small-businesses/client-accounting-services`  | Client accounting services for small businesses  |
| `/who-we-help/small-businesses/financial-reporting`         | Financial reporting for small businesses         |
| `/who-we-help/small-businesses/payroll-services`            | Payroll services for small businesses            |
| `/who-we-help/small-businesses/tax-preparation`             | Tax preparation for small businesses             |
| `/who-we-help/small-businesses/tax-planning`                | Tax planning for small businesses                |
| `/who-we-help/small-businesses/tax-compliance`              | Tax compliance for small businesses              |
| `/who-we-help/small-businesses/sales-tax-returns`           | Sales tax return support for small businesses    |
| `/who-we-help/small-businesses/expense-management`          | Expense management for small businesses          |
| `/who-we-help/small-businesses/budgeting-forecasting`       | Budgeting and forecasting for small businesses   |
| `/who-we-help/small-businesses/cash-flow-management`        | Cash flow management for small businesses        |
| `/who-we-help/small-businesses/outsourced-cfo-services`     | Outsourced CFO services for small businesses     |
| `/who-we-help/small-businesses/business-advisory-services`  | Business advisory services for small businesses  |

## Suggested Positioning

```txt
Hanover helps small businesses manage bookkeeping, monthly accounting, payroll, tax preparation, reporting, and advisory needs through secure online support and dedicated professional guidance.
```

## Related Services

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

---

# 11. Medium-Sized Businesses + Service Pages

Medium-sized business pages should focus on financial reporting, payroll, compliance, advisory, internal controls, cash flow, and higher-level planning.

## Page List

```txt
/who-we-help/medium-sized-businesses/monthly-accounting-services
/who-we-help/medium-sized-businesses/client-accounting-services
/who-we-help/medium-sized-businesses/financial-reporting
/who-we-help/medium-sized-businesses/payroll-services
/who-we-help/medium-sized-businesses/tax-preparation
/who-we-help/medium-sized-businesses/tax-planning
/who-we-help/medium-sized-businesses/tax-compliance
/who-we-help/medium-sized-businesses/sales-tax-returns
/who-we-help/medium-sized-businesses/budgeting-forecasting
/who-we-help/medium-sized-businesses/cash-flow-management
/who-we-help/medium-sized-businesses/outsourced-cfo-services
/who-we-help/medium-sized-businesses/business-advisory-services
/who-we-help/medium-sized-businesses/business-valuation
/who-we-help/medium-sized-businesses/succession-planning
/who-we-help/medium-sized-businesses/internal-controls-review
```

## Page Intent

| Page                                                               | Search Intent                                           |
| ------------------------------------------------------------------ | ------------------------------------------------------- |
| `/who-we-help/medium-sized-businesses/monthly-accounting-services` | Monthly accounting services for medium-sized businesses |
| `/who-we-help/medium-sized-businesses/client-accounting-services`  | Client accounting services for medium-sized businesses  |
| `/who-we-help/medium-sized-businesses/financial-reporting`         | Financial reporting for medium-sized businesses         |
| `/who-we-help/medium-sized-businesses/payroll-services`            | Payroll services for medium-sized businesses            |
| `/who-we-help/medium-sized-businesses/tax-preparation`             | Tax preparation for medium-sized businesses             |
| `/who-we-help/medium-sized-businesses/tax-planning`                | Tax planning for medium-sized businesses                |
| `/who-we-help/medium-sized-businesses/tax-compliance`              | Tax compliance for medium-sized businesses              |
| `/who-we-help/medium-sized-businesses/sales-tax-returns`           | Sales tax return support for medium-sized businesses    |
| `/who-we-help/medium-sized-businesses/budgeting-forecasting`       | Budgeting and forecasting for medium-sized businesses   |
| `/who-we-help/medium-sized-businesses/cash-flow-management`        | Cash flow management for medium-sized businesses        |
| `/who-we-help/medium-sized-businesses/outsourced-cfo-services`     | Outsourced CFO services for medium-sized businesses     |
| `/who-we-help/medium-sized-businesses/business-advisory-services`  | Business advisory services for medium-sized businesses  |
| `/who-we-help/medium-sized-businesses/business-valuation`          | Business valuation for medium-sized businesses          |
| `/who-we-help/medium-sized-businesses/succession-planning`         | Succession planning for medium-sized businesses         |
| `/who-we-help/medium-sized-businesses/internal-controls-review`    | Internal controls review for medium-sized businesses    |

## Suggested Positioning

```txt
Hanover helps medium-sized businesses strengthen accounting systems, improve reporting visibility, manage tax and payroll needs, and make better financial decisions through secure online advisory and accounting support.
```

## Related Services

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

---

# 12. Family-Owned Businesses + Service Pages

Family-owned business pages should focus on continuity, clean accounting, tax planning, succession, valuation, advisory support, and owner transitions.

## Page List

```txt
/who-we-help/family-owned-businesses/online-bookkeeping
/who-we-help/family-owned-businesses/monthly-accounting-services
/who-we-help/family-owned-businesses/client-accounting-services
/who-we-help/family-owned-businesses/financial-reporting
/who-we-help/family-owned-businesses/payroll-services
/who-we-help/family-owned-businesses/tax-preparation
/who-we-help/family-owned-businesses/tax-planning
/who-we-help/family-owned-businesses/tax-compliance
/who-we-help/family-owned-businesses/expense-management
/who-we-help/family-owned-businesses/budgeting-forecasting
/who-we-help/family-owned-businesses/cash-flow-management
/who-we-help/family-owned-businesses/outsourced-cfo-services
/who-we-help/family-owned-businesses/business-advisory-services
/who-we-help/family-owned-businesses/business-valuation
/who-we-help/family-owned-businesses/succession-planning
/who-we-help/family-owned-businesses/exit-strategy-planning
```

## Page Intent

| Page                                                               | Search Intent                                           |
| ------------------------------------------------------------------ | ------------------------------------------------------- |
| `/who-we-help/family-owned-businesses/online-bookkeeping`          | Online bookkeeping for family-owned businesses          |
| `/who-we-help/family-owned-businesses/monthly-accounting-services` | Monthly accounting services for family-owned businesses |
| `/who-we-help/family-owned-businesses/client-accounting-services`  | Client accounting services for family-owned businesses  |
| `/who-we-help/family-owned-businesses/financial-reporting`         | Financial reporting for family-owned businesses         |
| `/who-we-help/family-owned-businesses/payroll-services`            | Payroll services for family-owned businesses            |
| `/who-we-help/family-owned-businesses/tax-preparation`             | Tax preparation for family-owned businesses             |
| `/who-we-help/family-owned-businesses/tax-planning`                | Tax planning for family-owned businesses                |
| `/who-we-help/family-owned-businesses/tax-compliance`              | Tax compliance for family-owned businesses              |
| `/who-we-help/family-owned-businesses/expense-management`          | Expense management for family-owned businesses          |
| `/who-we-help/family-owned-businesses/budgeting-forecasting`       | Budgeting and forecasting for family-owned businesses   |
| `/who-we-help/family-owned-businesses/cash-flow-management`        | Cash flow management for family-owned businesses        |
| `/who-we-help/family-owned-businesses/outsourced-cfo-services`     | Outsourced CFO services for family-owned businesses     |
| `/who-we-help/family-owned-businesses/business-advisory-services`  | Business advisory services for family-owned businesses  |
| `/who-we-help/family-owned-businesses/business-valuation`          | Business valuation for family-owned businesses          |
| `/who-we-help/family-owned-businesses/succession-planning`         | Succession planning for family-owned businesses         |
| `/who-we-help/family-owned-businesses/exit-strategy-planning`      | Exit strategy planning for family-owned businesses      |

## Suggested Positioning

```txt
Hanover helps family-owned businesses manage accounting, tax, payroll, reporting, cash flow, advisory, valuation, and succession needs with secure online support and practical financial guidance.
```

## Related Services

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

---

# 13. Business Owners + Service Pages

Business owner pages should focus on owner decision-making, financial clarity, tax planning, cash flow, advisory support, valuation, succession, and exit strategy.

## Page List

```txt
/who-we-help/business-owners/online-bookkeeping
/who-we-help/business-owners/monthly-accounting-services
/who-we-help/business-owners/client-accounting-services
/who-we-help/business-owners/financial-reporting
/who-we-help/business-owners/payroll-services
/who-we-help/business-owners/tax-preparation
/who-we-help/business-owners/tax-planning
/who-we-help/business-owners/tax-compliance
/who-we-help/business-owners/expense-management
/who-we-help/business-owners/budgeting-forecasting
/who-we-help/business-owners/cash-flow-management
/who-we-help/business-owners/outsourced-cfo-services
/who-we-help/business-owners/business-advisory-services
/who-we-help/business-owners/business-valuation
/who-we-help/business-owners/succession-planning
/who-we-help/business-owners/exit-strategy-planning
```

## Page Intent

| Page                                                       | Search Intent                                   |
| ---------------------------------------------------------- | ----------------------------------------------- |
| `/who-we-help/business-owners/online-bookkeeping`          | Online bookkeeping for business owners          |
| `/who-we-help/business-owners/monthly-accounting-services` | Monthly accounting services for business owners |
| `/who-we-help/business-owners/client-accounting-services`  | Client accounting services for business owners  |
| `/who-we-help/business-owners/financial-reporting`         | Financial reporting for business owners         |
| `/who-we-help/business-owners/payroll-services`            | Payroll services for business owners            |
| `/who-we-help/business-owners/tax-preparation`             | Tax preparation for business owners             |
| `/who-we-help/business-owners/tax-planning`                | Tax planning for business owners                |
| `/who-we-help/business-owners/tax-compliance`              | Tax compliance for business owners              |
| `/who-we-help/business-owners/expense-management`          | Expense management for business owners          |
| `/who-we-help/business-owners/budgeting-forecasting`       | Budgeting and forecasting for business owners   |
| `/who-we-help/business-owners/cash-flow-management`        | Cash flow management for business owners        |
| `/who-we-help/business-owners/outsourced-cfo-services`     | Outsourced CFO services for business owners     |
| `/who-we-help/business-owners/business-advisory-services`  | Business advisory services for business owners  |
| `/who-we-help/business-owners/business-valuation`          | Business valuation for business owners          |
| `/who-we-help/business-owners/succession-planning`         | Succession planning for business owners         |
| `/who-we-help/business-owners/exit-strategy-planning`      | Exit strategy planning for business owners      |

## Suggested Positioning

```txt
Hanover helps business owners understand financial performance, manage accounting and tax responsibilities, plan for cash flow, and make more informed business decisions through secure online accounting and advisory services.
```

## Related Services

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

---

# 14. Growing Companies + Service Pages

Growing company pages should focus on scaling accounting systems, better reporting, payroll, compliance, cash flow, CFO support, advisory, investor readiness, and internal controls.

## Page List

```txt
/who-we-help/growing-companies/monthly-accounting-services
/who-we-help/growing-companies/client-accounting-services
/who-we-help/growing-companies/financial-reporting
/who-we-help/growing-companies/payroll-services
/who-we-help/growing-companies/tax-preparation
/who-we-help/growing-companies/tax-planning
/who-we-help/growing-companies/tax-compliance
/who-we-help/growing-companies/sales-tax-returns
/who-we-help/growing-companies/budgeting-forecasting
/who-we-help/growing-companies/cash-flow-management
/who-we-help/growing-companies/outsourced-cfo-services
/who-we-help/growing-companies/business-advisory-services
/who-we-help/growing-companies/fundraising-investor-relations
/who-we-help/growing-companies/internal-controls-review
```

## Page Intent

| Page                                                            | Search Intent                                                    |
| --------------------------------------------------------------- | ---------------------------------------------------------------- |
| `/who-we-help/growing-companies/monthly-accounting-services`    | Monthly accounting services for growing companies                |
| `/who-we-help/growing-companies/client-accounting-services`     | Client accounting services for growing companies                 |
| `/who-we-help/growing-companies/financial-reporting`            | Financial reporting for growing companies                        |
| `/who-we-help/growing-companies/payroll-services`               | Payroll services for growing companies                           |
| `/who-we-help/growing-companies/tax-preparation`                | Tax preparation for growing companies                            |
| `/who-we-help/growing-companies/tax-planning`                   | Tax planning for growing companies                               |
| `/who-we-help/growing-companies/tax-compliance`                 | Tax compliance for growing companies                             |
| `/who-we-help/growing-companies/sales-tax-returns`              | Sales tax return support for growing companies                   |
| `/who-we-help/growing-companies/budgeting-forecasting`          | Budgeting and forecasting for growing companies                  |
| `/who-we-help/growing-companies/cash-flow-management`           | Cash flow management for growing companies                       |
| `/who-we-help/growing-companies/outsourced-cfo-services`        | Outsourced CFO services for growing companies                    |
| `/who-we-help/growing-companies/business-advisory-services`     | Business advisory services for growing companies                 |
| `/who-we-help/growing-companies/fundraising-investor-relations` | Fundraising and investor relations support for growing companies |
| `/who-we-help/growing-companies/internal-controls-review`       | Internal controls review for growing companies                   |

## Suggested Positioning

```txt
Hanover helps growing companies strengthen accounting operations, improve reporting, manage tax and payroll responsibilities, prepare for growth decisions, and add higher-level financial guidance through secure online services.
```

## Related Services

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

# 15. Metadata Patterns

Each audience + service page needs unique metadata.

## Title Tag Pattern

```txt
[Service] for [Audience] | Hanover Accountants & Advisors
```

Examples:

```txt
Online Bookkeeping for Startups | Hanover Accountants & Advisors
Tax Preparation for Small Businesses | Hanover Accountants & Advisors
Outsourced CFO Services for Family-Owned Businesses | Hanover Accountants & Advisors
```

## Meta Description Pattern

```txt
Hanover provides [service] for [audience] through secure online workflows and professional support. Schedule a consultation to discuss your accounting, tax, payroll, or advisory needs.
```

## H1 Pattern

```txt
[Service] for [Audience]
```

Examples:

```txt
Online Bookkeeping for Startups
Tax Preparation for Small Businesses
Outsourced CFO Services for Family-Owned Businesses
```

## Direct Answer Pattern

```txt
Hanover provides [service] for [audience] through secure online workflows, dedicated professional support, and a consultation-based process designed around the client's needs.
```

---

# 16. Schema Strategy

Audience + service pages should generally use:

```txt
Service
FAQPage
BreadcrumbList
```

## Schema Inputs

Each page should include:

```txt
Service name
Service description
Provider name
Audience description
Area served: United States
URL
FAQs
Breadcrumbs
```

## Schema Rules

Do not add:

```txt
Fake reviews
Fake aggregate ratings
Fake prices
Fake guarantees
Fake business hours
Fake local office details
```

---

# 17. Internal Linking Rules

Each audience + service page should link to:

```txt
Parent audience page
Core service page
Related service pages
Related resource articles
Relevant FAQ page
Nationwide + service page
Schedule consultation page
```

## Example

For:

```txt
/who-we-help/startups/online-bookkeeping
```

Link to:

```txt
/who-we-help/startups
/services/online-bookkeeping
/services/monthly-accounting-services
/services/financial-reporting
/service-areas/nationwide/online-bookkeeping
/resources/bookkeeping/what-is-online-bookkeeping
/faqs/online-bookkeeping
/schedule-consultation
```

---

# 18. Content Quality Rules

Every audience + service page must be unique.

Do not create:

```txt
Audience-name swap pages
Thin matrix pages
Duplicate service descriptions
Duplicate FAQs across the full matrix
Unsupported audience claims
Fake case studies
Fake savings claims
Fake testimonials
Fake guarantees
```

Each page should include:

```txt
Specific audience context
Specific service explanation
Specific problems solved
Specific workflow explanation
Unique FAQs
Related links
Clear CTA
Metadata
Schema
```

---

# 19. Recommended Dynamic Route

Use this route:

```txt
app/who-we-help/[audience]/[service]/page.tsx
```

Use `generateStaticParams` from:

```txt
src/data/audienceServiceMatrix.ts
```

The route should validate that:

```txt
Audience exists
Service exists
Audience + service pair is approved
Page is marked includeInIndex
Page has metadata
Page has schema inputs
```

---

# 20. Recommended Matrix Data Structure

```ts
export const audienceServiceMatrix = [
  {
    audienceSlug: "startups",
    serviceSlug: "online-bookkeeping",
    path: "/who-we-help/startups/online-bookkeeping",
    title: "Online Bookkeeping for Startups",
    h1: "Online Bookkeeping for Startups",
    metaTitle: "Online Bookkeeping for Startups | Hanover Accountants & Advisors",
    metaDescription:
      "Hanover provides online bookkeeping for startups through secure workflows and professional support for organized financial records and clearer reporting.",
    primaryIntent: "online bookkeeping for startups",
    includeInSitemap: true,
    includeInIndex: true,
  },
];
```

---

# 21. QA Checklist

Before publishing the audience + service matrix, verify:

```txt
Every audience slug exists in audiences.ts.
Every service slug exists in services.ts.
Every matrix route generates correctly.
Every page has a unique H1.
Every page has a unique title tag.
Every page has a unique meta description.
Every page has a direct answer section.
Every page has unique audience-specific content.
Every page has relevant FAQs.
Every page links to the parent audience page.
Every page links to the core service page.
Every page links to the consultation page.
Every page has breadcrumb schema.
Every page has service schema.
Every page appears in sitemap.xml.
No page contains fake claims.
No page contains fake testimonials.
No page contains fake pricing.
No page contains fake guarantees.
```

---

# 22. Final Audience Matrix Direction

The audience + service matrix gives Hanover a strong structure for audience-specific search and conversion.

The final matrix should include:

```txt
8 audience pages
103 audience + service pages
```

The audience section should help users quickly understand whether Hanover serves their situation, which services are most relevant, and how to schedule a consultation.

The pages must be built individually with useful content, clear intent, unique FAQs, internal links, schema, and conversion CTAs.
