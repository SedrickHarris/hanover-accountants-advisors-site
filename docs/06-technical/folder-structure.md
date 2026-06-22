# Folder Structure

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the recommended local project folder structure for the Hanover Accountants & Advisors website rebuild.

The project will be built with:

* Next.js App Router
* TypeScript
* Static export
* Cloudflare Pages
* GitHub
* Claude Code
* VS Code
* Data-driven page generation
* Reusable components
* Centralized content data
* SEO metadata
* JSON-LD schema
* Sitemap generation
* Local and nationwide page matrices

The folder structure must support a large, scalable website with hundreds of static pages while remaining clean, maintainable, and easy for Claude Code to work with.

---

# 1. Recommended Local Project Path

Use the client-sites directory pattern.

```txt
C:\Users\Welcome\Desktop\client-sites\hanover-aa-site
```

> ⚠️ **Naming note:** The repo and folder actually in use are
> `hanover-accountants-advisors-site` (remote:
> https://github.com/SedrickHarris/hanover-accountants-advisors-site.git). The
> `hanover-aa-site` name below is the doc's recommendation; reconcile before launch
> if a shorter name is preferred.

## Recommended GitHub Repository Name

```txt
hanover-aa-site
```

## Recommended GitHub Remote

```txt
https://github.com/SedrickHarris/hanover-aa-site.git
```

Confirm the final repository name before pushing.

---

# 2. Root Folder Structure

Recommended project root:

```txt
hanover-aa-site/
  app/
  public/
  src/
  docs/
  scripts/
  .gitignore
  README.md
  CLAUDE.md
  next.config.ts
  package.json
  package-lock.json
  postcss.config.mjs
  tailwind.config.ts
  tsconfig.json
  eslint.config.mjs
```

## Root Folder Purpose

| Folder or File   | Purpose                                                                               |
| ---------------- | ------------------------------------------------------------------------------------- |
| `app/`           | Next.js App Router pages, layouts, route groups, metadata, and route templates        |
| `public/`        | Static assets such as images, favicons, OG images, robots.txt, and redirects          |
| `src/`           | Components, data, utilities, schema, metadata helpers, and shared logic               |
| `docs/`          | Project documentation, strategy docs, handoff prompts, build plans, and QA checklists |
| `scripts/`       | Build helpers, sitemap tools, route validation, and optional automation scripts       |
| `README.md`      | Project overview and developer instructions                                           |
| `CLAUDE.md`      | Claude Code operating instructions                                                    |
| `next.config.ts` | Static export configuration                                                           |
| `package.json`   | Project scripts and dependencies                                                      |
| `tsconfig.json`  | TypeScript configuration                                                              |

---

# 3. App Router Structure

Recommended `app/` structure:

```txt
app/
  layout.tsx
  page.tsx
  globals.css
  not-found.tsx

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

  privacy-policy/
    page.tsx

  terms-of-use/
    page.tsx

  sitemap/
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

# 4. App Router Page Purpose

## Core Pages

```txt
app/page.tsx
app/about/page.tsx
app/contact/page.tsx
app/schedule-consultation/page.tsx
app/get-started/page.tsx
app/client-portal/page.tsx
app/privacy-policy/page.tsx
app/terms-of-use/page.tsx
app/sitemap/page.tsx
app/not-found.tsx
```

## Service Pages

```txt
app/services/page.tsx
app/services/accounting/page.tsx
app/services/tax/page.tsx
app/services/advisory/page.tsx
app/services/[service]/page.tsx
```

## Audience Pages

```txt
app/who-we-help/page.tsx
app/who-we-help/[audience]/page.tsx
app/who-we-help/[audience]/[service]/page.tsx
```

## Service Area Pages

```txt
app/service-areas/page.tsx
app/service-areas/nationwide/page.tsx
app/service-areas/nationwide/[service]/page.tsx
app/service-areas/[location]/page.tsx
app/service-areas/[location]/[service]/page.tsx
```

## Industry Pages

```txt
app/industries/page.tsx
app/industries/[industry]/page.tsx
app/industries/[industry]/[service]/page.tsx
```

## Resource Pages

```txt
app/resources/page.tsx
app/resources/[category]/page.tsx
app/resources/[category]/[slug]/page.tsx
```

## FAQ Pages

```txt
app/faqs/page.tsx
app/faqs/[category]/page.tsx
```

---

# 5. Source Folder Structure

Recommended `src/` structure:

```txt
src/
  components/
    layout/
    sections/
    cards/
    ui/
    forms/
    schema/
    seo/

  data/
    site.ts
    navigation.ts
    ctas.ts
    services.ts
    serviceCategories.ts
    audiences.ts
    audienceServiceMatrix.ts
    serviceAreas.ts
    locationServiceMatrix.ts
    industries.ts
    resources.ts
    faqs.ts
    metadata.ts
    schema.ts
    redirects.ts

  lib/
    metadata.ts
    schema.ts
    routes.ts
    sitemap.ts
    urls.ts
    format.ts
    validators.ts

  templates/
    ServicePageTemplate.tsx
    ServiceCategoryTemplate.tsx
    AudiencePageTemplate.tsx
    AudienceServicePageTemplate.tsx
    ServiceAreaPageTemplate.tsx
    NationwideServicePageTemplate.tsx
    LocationServicePageTemplate.tsx
    IndustryPageTemplate.tsx
    ResourceCategoryTemplate.tsx
    ResourceArticleTemplate.tsx
    FAQPageTemplate.tsx

  types/
    site.ts
    services.ts
    audiences.ts
    serviceAreas.ts
    industries.ts
    resources.ts
    faqs.ts
    metadata.ts
    schema.ts
```

---

# 6. Components Folder

Recommended `src/components/` structure:

```txt
src/components/
  layout/
    Header.tsx
    Footer.tsx
    MobileNav.tsx
    MainNav.tsx
    Breadcrumbs.tsx
    Container.tsx

  sections/
    Hero.tsx
    DirectAnswer.tsx
    ServiceGrid.tsx
    AudienceGrid.tsx
    ServiceAreaGrid.tsx
    IndustryGrid.tsx
    ResourceGrid.tsx
    FAQSection.tsx
    CTASection.tsx
    RelatedLinks.tsx
    ProcessSection.tsx
    TrustSection.tsx
    SplitContent.tsx
    StatBand.tsx
    FeatureList.tsx
    SecureWorkflowSection.tsx

  cards/
    ServiceCard.tsx
    AudienceCard.tsx
    LocationCard.tsx
    IndustryCard.tsx
    ResourceCard.tsx
    FAQCard.tsx

  ui/
    Button.tsx
    Card.tsx
    Badge.tsx
    SectionHeading.tsx
    Icon.tsx
    LinkButton.tsx
    Divider.tsx

  forms/
    ContactForm.tsx
    ConsultationForm.tsx
    NewsletterForm.tsx

  schema/
    JsonLd.tsx

  seo/
    PageHeader.tsx
    MetaDebug.tsx
```

## Component Rules

Components should be:

```txt
Reusable
Typed with TypeScript
Responsive
Accessible
Cleanly named
Easy for Claude Code to modify
Free of hardcoded page-specific copy where data should be used instead
```

---

# 7. Layout Components

## Recommended Files

```txt
src/components/layout/Header.tsx
src/components/layout/Footer.tsx
src/components/layout/MobileNav.tsx
src/components/layout/MainNav.tsx
src/components/layout/Breadcrumbs.tsx
src/components/layout/Container.tsx
```

## Purpose

Layout components should control:

```txt
Global header
Main navigation
Mobile navigation
Footer
Breadcrumbs
Content width
Page spacing
Reusable layout wrappers
```

The header and footer should pull from:

```txt
src/data/navigation.ts
src/data/site.ts
src/data/ctas.ts
```

---

# 8. Section Components

## Recommended Files

```txt
src/components/sections/Hero.tsx
src/components/sections/DirectAnswer.tsx
src/components/sections/ServiceGrid.tsx
src/components/sections/AudienceGrid.tsx
src/components/sections/ServiceAreaGrid.tsx
src/components/sections/IndustryGrid.tsx
src/components/sections/ResourceGrid.tsx
src/components/sections/FAQSection.tsx
src/components/sections/CTASection.tsx
src/components/sections/RelatedLinks.tsx
src/components/sections/ProcessSection.tsx
src/components/sections/TrustSection.tsx
src/components/sections/SecureWorkflowSection.tsx
```

## Purpose

Section components should support reusable page construction across:

```txt
Homepage
Service pages
Audience pages
Audience + service pages
Nationwide pages
Local service-area pages
Local + service pages
Industry pages
Resources
FAQs
```

---

# 9. Card Components

## Recommended Files

```txt
src/components/cards/ServiceCard.tsx
src/components/cards/AudienceCard.tsx
src/components/cards/LocationCard.tsx
src/components/cards/IndustryCard.tsx
src/components/cards/ResourceCard.tsx
src/components/cards/FAQCard.tsx
```

## Purpose

Card components should display:

```txt
Service summaries
Audience summaries
Location summaries
Industry summaries
Resource summaries
FAQ previews
Related links
```

Cards should avoid hardcoded text where possible.

They should receive props from the data layer.

---

# 10. UI Components

## Recommended Files

```txt
src/components/ui/Button.tsx
src/components/ui/Card.tsx
src/components/ui/Badge.tsx
src/components/ui/SectionHeading.tsx
src/components/ui/Icon.tsx
src/components/ui/LinkButton.tsx
src/components/ui/Divider.tsx
```

## Purpose

UI components should control small reusable design patterns.

They should be:

```txt
Accessible
Keyboard-friendly
Consistent
Responsive
Token-based
Easy to reuse
```

---

# 11. Form Components

## Recommended Files

```txt
src/components/forms/ContactForm.tsx
src/components/forms/ConsultationForm.tsx
src/components/forms/NewsletterForm.tsx
```

## Form Notes

Forms should be implemented based on the final approved platform.

Before launch, confirm:

```txt
Form provider
Form destination
Notification email
CRM integration
Spam protection
Required fields
Privacy language
Thank-you behavior
```

If no live integration is approved during scaffold, use placeholder forms with clear TODO comments.

---

# 12. Schema Components

## Recommended File

```txt
src/components/schema/JsonLd.tsx
```

## Purpose

This component renders JSON-LD schema on pages.

Example:

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

# 13. Data Folder

Recommended `src/data/` structure:

```txt
src/data/
  site.ts
  navigation.ts
  ctas.ts
  services.ts
  serviceCategories.ts
  audiences.ts
  audienceServiceMatrix.ts
  serviceAreas.ts
  locationServiceMatrix.ts
  industries.ts
  resources.ts
  faqs.ts
  metadata.ts
  schema.ts
  redirects.ts
```

## Data File Purpose

| File                       | Purpose                                                   |
| -------------------------- | --------------------------------------------------------- |
| `site.ts`                  | Business name, URLs, contact information, global settings |
| `navigation.ts`            | Header, footer, dropdown, and mobile navigation           |
| `ctas.ts`                  | Approved CTA labels and CTA destinations                  |
| `services.ts`              | Core service data                                         |
| `serviceCategories.ts`     | Accounting, tax, and advisory service groups              |
| `audiences.ts`             | Audience page data                                        |
| `audienceServiceMatrix.ts` | Audience + service page matrix                            |
| `serviceAreas.ts`          | Nationwide and local service-area data                    |
| `locationServiceMatrix.ts` | Local + service page matrix                               |
| `industries.ts`            | Industry page data                                        |
| `resources.ts`             | Resource category and article data                        |
| `faqs.ts`                  | FAQ category and question data                            |
| `metadata.ts`              | Shared metadata defaults and patterns                     |
| `schema.ts`                | Base schema entity data                                   |
| `redirects.ts`             | Redirect mapping data                                     |

---

# 14. Site Data File

Recommended file:

```txt
src/data/site.ts
```

## Purpose

This file should centralize verified business information.

## Suggested Structure

```ts
export const siteConfig = {
  name: "Hanover Accountants & Advisors",
  domain: "https://www.hanoveraa.com",
  description:
    "Nationwide online accounting, bookkeeping, tax preparation, payroll, outsourced CFO, and advisory services.",
  phone: "404-952-6800",
  email: "sales@hanoveraa.com",
  primaryCta: {
    label: "Schedule a Consultation",
    href: "/schedule-consultation",
  },
  clientPortal: {
    label: "Client Portal",
    href: "/client-portal",
  },
};
```

## Confirmation Required

Before launch, confirm:

```txt
Final business name
Final domain
Phone numbers
Email addresses
Office addresses
Client portal URL
Business hours
Social profile links
```

---

# 15. Navigation Data File

Recommended file:

```txt
src/data/navigation.ts
```

## Purpose

This file should control:

```txt
Main navigation
Dropdown navigation
Mobile navigation
Footer navigation
Utility links
CTA links
```

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

---

# 16. Services Data Files

Recommended files:

```txt
src/data/services.ts
src/data/serviceCategories.ts
```

## Purpose

These files should power:

```txt
Service hub
Service category hubs
Individual service pages
Related services
Audience + service pages
Nationwide + service pages
Local + service pages
Industry pages
Metadata
Schema
Sitemap
```

---

# 17. Audience Data Files

Recommended files:

```txt
src/data/audiences.ts
src/data/audienceServiceMatrix.ts
```

## Purpose

These files should power:

```txt
Audience hub
Audience pages
Audience + service pages
Audience-specific internal links
Metadata
Schema
Sitemap
Static route generation
```

---

# 18. Service Area Data Files

Recommended files:

```txt
src/data/serviceAreas.ts
src/data/locationServiceMatrix.ts
```

## Purpose

These files should power:

```txt
Service areas hub
Nationwide service-area page
Nationwide + service pages
Local service-area pages
Local + service pages
Nearby market links
Metadata
Schema
Sitemap
Static route generation
```

---

# 19. Industries Data File

Recommended file:

```txt
src/data/industries.ts
```

## Purpose

This file should power:

```txt
Industries hub
Industry pages
Optional industry + service pages
Related service links
Resource links
Metadata
Schema
Sitemap
```

---

# 20. Resources Data File

Recommended file:

```txt
src/data/resources.ts
```

## Purpose

This file should power:

```txt
Resource hub
Resource category pages
Resource article pages
Related article links
Related service CTAs
Article metadata
Article schema
Sitemap
```

---

# 21. FAQ Data File

Recommended file:

```txt
src/data/faqs.ts
```

## Purpose

This file should power:

```txt
FAQ hub
FAQ category pages
FAQ sections on service pages
FAQ sections on resource pages
FAQ schema
AEO content blocks
People Also Ask targeting
```

---

# 22. Library Folder

Recommended `src/lib/` structure:

```txt
src/lib/
  metadata.ts
  schema.ts
  routes.ts
  sitemap.ts
  urls.ts
  format.ts
  validators.ts
```

## Library File Purpose

| File            | Purpose                          |
| --------------- | -------------------------------- |
| `metadata.ts`   | Metadata builder functions       |
| `schema.ts`     | JSON-LD schema builder functions |
| `routes.ts`     | Route generation utilities       |
| `sitemap.ts`    | Sitemap entry generation         |
| `urls.ts`       | Canonical URL and path helpers   |
| `format.ts`     | Formatting utilities             |
| `validators.ts` | Data validation helpers          |

---

# 23. Template Folder

Recommended `src/templates/` structure:

```txt
src/templates/
  ServicePageTemplate.tsx
  ServiceCategoryTemplate.tsx
  AudiencePageTemplate.tsx
  AudienceServicePageTemplate.tsx
  ServiceAreaPageTemplate.tsx
  NationwideServicePageTemplate.tsx
  LocationServicePageTemplate.tsx
  IndustryPageTemplate.tsx
  ResourceCategoryTemplate.tsx
  ResourceArticleTemplate.tsx
  FAQPageTemplate.tsx
```

## Template Purpose

Templates should allow many pages to share structure while using unique data.

Templates should control:

```txt
Page sections
Component layout
Related links
FAQ rendering
CTA placement
Schema rendering
Metadata support
```

Templates should not create duplicate content.

Each page must still receive unique content from the data layer.

---

# 24. Types Folder

Recommended `src/types/` structure:

```txt
src/types/
  site.ts
  services.ts
  audiences.ts
  serviceAreas.ts
  industries.ts
  resources.ts
  faqs.ts
  metadata.ts
  schema.ts
```

## Purpose

The types folder should centralize TypeScript types for:

```txt
Services
Audiences
Locations
Industries
Resources
FAQs
Metadata
Schema
Site settings
Navigation
```

This keeps the build safer as the page count grows.

---

# 25. Public Folder Structure

Recommended `public/` structure:

```txt
public/
  favicon.ico
  robots.txt
  sitemap.xml
  _redirects

  images/
    brand/
    og/
    icons/
    services/
    audiences/
    service-areas/
    industries/
    resources/
    backgrounds/
```

## Public Folder Purpose

| Folder or File          | Purpose                                  |
| ----------------------- | ---------------------------------------- |
| `favicon.ico`           | Browser favicon                          |
| `robots.txt`            | Search crawler directives                |
| `sitemap.xml`           | XML sitemap                              |
| `_redirects`            | Cloudflare Pages redirect rules, if used |
| `images/brand/`         | Logos and brand assets                   |
| `images/og/`            | Open Graph images                        |
| `images/icons/`         | UI icons and favicons                    |
| `images/services/`      | Service page images                      |
| `images/audiences/`     | Audience page images                     |
| `images/service-areas/` | Service-area page images                 |
| `images/industries/`    | Industry page images                     |
| `images/resources/`     | Resource article images                  |
| `images/backgrounds/`   | Background textures or visual assets     |

---

# 26. Image Folder Rules

Images should be organized by purpose.

## Recommended Format

Use:

```txt
.webp
.svg for simple icons and logos
.png only when transparency or source needs require it
.jpg only when appropriate for photos
```

## Image Naming Rules

Use lowercase, hyphenated, SEO-friendly names.

Good:

```txt
hanover-online-bookkeeping-services.webp
hanover-tax-preparation-services.webp
hanover-nationwide-accounting-services-og.jpg
hanover-accounting-advisory-logo.svg
```

Avoid:

```txt
IMG_1234.png
final-final-logo.png
tax image.jpg
New Hero 2.webp
```

---

# 27. Documentation Folder

Recommended `docs/` structure:

```txt
docs/
  README.md
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

  build-phases/
    phase-01-foundation.md
    phase-02-services.md
    phase-03-nationwide.md
    phase-04-audiences.md
    phase-05-local-service-areas.md
    phase-06-industries.md
    phase-07-resources-faqs.md
    phase-08-launch-qa.md

  qa/
    metadata-qa.md
    schema-qa.md
    internal-linking-qa.md
    content-qa.md
    accessibility-qa.md
    performance-qa.md
    redirect-qa.md

  prompts/
    homepage-build-prompt.md
    services-build-prompt.md
    audience-build-prompt.md
    location-build-prompt.md
    resource-build-prompt.md
    launch-qa-prompt.md
```

> **Note:** In this repository the docs are organized under numbered subfolders
> (`00-project-control`, `01-research`, `02-strategy`, `03-seo-aeo-geo`,
> `04-brand-content`, `05-matrices`, `06-technical`, `07-claude-project`,
> `08-qa-launch`) rather than the flat layout above. The flat list here documents
> the originally recommended set; the numbered structure is the one in use.

## Documentation Rule

Keep all strategy and planning files in `docs/`.

Do not bury build instructions only in chat history.

---

# 28. Scripts Folder

Recommended `scripts/` structure:

```txt
scripts/
  generate-sitemap.ts
  validate-routes.ts
  validate-metadata.ts
  validate-schema.ts
  validate-internal-links.ts
```

## Script Purpose

Scripts may help validate:

```txt
All routes generate
All indexable pages are in sitemap
All metadata is unique
All schema objects are valid
All internal links point to existing routes
All matrix pages use approved slugs
```

Scripts are optional for the first scaffold but useful for a large static site.

---

# 29. Static Export Output

The static export output folder will be:

```txt
out/
```

This folder is generated by the build process.

Do not manually create or edit files in `out/`.

Do not commit `out/` unless the deployment workflow specifically requires it.

For Cloudflare Pages, set:

```txt
Build command: npm run build
Output directory: out
```

---

# 30. Git Ignore Rules

Recommended `.gitignore` should include:

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
Environment variables
Node modules
Build output
Local cache files
Private credentials
Client secrets
```

---

# 31. Recommended Package Scripts

Recommended `package.json` scripts:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "typecheck": "tsc --noEmit"
  }
}
```

For static export, `next build` should produce the `out/` folder when `output: "export"` is configured in `next.config.ts`.

---

# 32. Route Generation Rules

Dynamic routes must use `generateStaticParams`.

Required routes:

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

## Route Validation

Each dynamic route should validate:

```txt
Requested slug exists
Requested matrix combination is approved
Page has metadata
Page has content
Page has schema inputs
Page should be indexed
```

Invalid slugs should call:

```txt
notFound()
```

---

# 33. Sitemap File Placement

For static export, the sitemap should be available at:

```txt
public/sitemap.xml
```

Or generated into:

```txt
out/sitemap.xml
```

The final approach depends on the build script.

Recommended first build:

```txt
Generate or maintain public/sitemap.xml from known route data.
```

Later improvement:

```txt
Use a script to generate sitemap.xml from src/data route arrays.
```

---

# 34. Robots File Placement

Use:

```txt
public/robots.txt
```

Recommended launch version:

```txt
User-agent: *
Allow: /

Sitemap: https://www.hanoveraa.com/sitemap.xml
```

Do not block important sections from indexing unless intentionally required.

---

# 35. Redirect File Placement

For Cloudflare Pages, use:

```txt
public/_redirects
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

Confirm old URLs before launch.

---

# 36. Environment Variables

If environment variables are needed, use:

```txt
.env.local
```

Do not commit environment files.

Potential variables:

```txt
NEXT_PUBLIC_SITE_URL=https://www.hanoveraa.com
NEXT_PUBLIC_GA_ID=
NEXT_PUBLIC_GTM_ID=
NEXT_PUBLIC_FORM_ENDPOINT=
```

Only add variables that are actually needed.

---

# 37. Claude Code Working Rules

Claude Code should:

```txt
Read README.md first.
Read CLAUDE.md second.
Read docs/project-overview.md third.
Follow docs/do-not-invent.md.
Follow docs/site-architecture.md.
Follow docs/folder-structure.md.
Use data files for scalable content.
Use templates for repeated page types.
Avoid hardcoding large page matrices directly in page components.
Preserve static export compatibility.
Do not create API routes unless approved.
Do not invent claims.
Do not use fake office language.
```

---

# 38. Recommended Build Order

## Phase 1: Scaffold

```txt
Create Next.js project
Configure static export
Add base folders
Add README.md
Add CLAUDE.md
Add docs
Add global layout
Add header and footer
Add basic styles
```

## Phase 2: Data Layer

```txt
Create site.ts
Create navigation.ts
Create services.ts
Create serviceCategories.ts
Create audiences.ts
Create serviceAreas.ts
Create industries.ts
Create resources.ts
Create faqs.ts
```

## Phase 3: Templates

```txt
Create service template
Create audience template
Create service area template
Create resource template
Create FAQ template
Create related links system
Create CTA sections
```

## Phase 4: Routes

```txt
Build core pages
Build service routes
Build audience routes
Build service-area routes
Build industry routes
Build resource routes
Build FAQ routes
```

## Phase 5: SEO and Launch

```txt
Add metadata helpers
Add schema helpers
Add sitemap
Add robots.txt
Add redirects
Run QA
Build static export
Deploy to Cloudflare Pages
```

---

# 39. Folder Structure QA Checklist

Before build handoff, confirm:

```txt
Root folder exists.
Next.js project initializes correctly.
App Router is enabled.
TypeScript is enabled.
Static export is configured.
Tailwind is configured if used.
Core folders exist.
Docs folder contains all planning documents.
Data folder exists.
Components folder exists.
Templates folder exists.
Lib folder exists.
Types folder exists.
Public image folders exist.
robots.txt exists.
_redirects exists if redirects are needed.
sitemap.xml plan is defined.
out folder is generated by build.
out folder is ignored by Git.
```

---

# 40. Final Folder Structure Direction

The Hanover site should be built as a scalable, data-driven static Next.js project.

The structure should support:

```txt
Large page matrix generation
Static export
Cloudflare Pages deployment
Reusable templates
Centralized content data
Metadata generation
Schema generation
Sitemap generation
Internal linking
SEO
GEO
AEO
Local service-area visibility
Nationwide service visibility
LLM search visibility
Conversion
```

The folder structure should remain clean, predictable, and easy for Claude Code and future developers to maintain.
