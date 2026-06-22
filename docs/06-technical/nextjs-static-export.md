# Next.js Static Export

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the Next.js static export requirements for the Hanover Accountants & Advisors website rebuild.

The project will be built with:

* Next.js App Router
* TypeScript
* Static export
* Cloudflare Pages
* GitHub
* VS Code
* Claude Code
* Data-driven page generation
* Static HTML output
* `/out` deployment folder

The goal is to build a fast, scalable, search-friendly static website that can be deployed to Cloudflare Pages without requiring a Node.js server at runtime.

---

# 1. Static Export Goal

The Hanover website must build into a static export.

Final output folder:

```txt
out
```

Cloudflare Pages should use:

```txt
Build command: npm run build
Output directory: out
```

The deployed site should work without:

```txt
Next.js server runtime
Node server
API routes
Server actions
Dynamic server rendering
Runtime database access
Runtime CMS calls
```

---

# 2. Required Next.js Configuration

Use `next.config.ts`.

Recommended file:

```txt
next.config.ts
```

Recommended configuration:

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

## Why This Configuration Is Required

```txt
output: "export" tells Next.js to generate static HTML output.
trailingSlash: true creates clean folder-based static routes.
images.unoptimized: true avoids runtime image optimization requirements.
```

---

# 3. Static Export Output

After running:

```txt
npm run build
```

Next.js should generate:

```txt
out/
```

The `out/` folder should contain static HTML, JavaScript, CSS, and assets ready for Cloudflare Pages.

Do not manually edit the `out/` folder.

Do not rely on files that only exist in `.next/`.

---

# 4. Package Scripts

Recommended `package.json` scripts:

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

If the project uses an ESLint setup that does not support `next lint`, use the project's configured lint command.

The key command for deployment is:

```txt
npm run build
```

---

# 5. App Router Compatibility

The site should use the Next.js App Router.

Recommended page folder:

```txt
app/
```

Core files:

```txt
app/layout.tsx
app/page.tsx
app/globals.css
app/not-found.tsx
```

Dynamic pages must generate static paths at build time.

---

# 6. Dynamic Route Requirement

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

## Rule

If a page uses a dynamic segment, the allowed paths must be known at build time.

Do not depend on runtime discovery.

---

# 7. Example Static Params for Service Pages

Route:

```txt
app/services/[service]/page.tsx
```

Example:

```tsx
import { notFound } from "next/navigation";
import { services } from "@/data/services";
import { ServicePageTemplate } from "@/templates/ServicePageTemplate";

export function generateStaticParams() {
  return services.map((service) => ({
    service: service.slug,
  }));
}

export function generateMetadata({ params }: { params: { service: string } }) {
  const service = services.find((item) => item.slug === params.service);

  if (!service) {
    return {};
  }

  return {
    title: service.metaTitle,
    description: service.metaDescription,
    alternates: {
      canonical: service.path,
    },
  };
}

export default function ServicePage({ params }: { params: { service: string } }) {
  const service = services.find((item) => item.slug === params.service);

  if (!service) {
    notFound();
  }

  return <ServicePageTemplate service={service} />;
}
```

---

# 8. Example Static Params for Audience + Service Pages

Route:

```txt
app/who-we-help/[audience]/[service]/page.tsx
```

Example:

```tsx
import { notFound } from "next/navigation";
import { audiences } from "@/data/audiences";
import { services } from "@/data/services";
import { audienceServiceMatrix } from "@/data/audienceServiceMatrix";
import { AudienceServicePageTemplate } from "@/templates/AudienceServicePageTemplate";

export function generateStaticParams() {
  return audienceServiceMatrix.map((item) => ({
    audience: item.audienceSlug,
    service: item.serviceSlug,
  }));
}

export default function AudienceServicePage({
  params,
}: {
  params: { audience: string; service: string };
}) {
  const matrixItem = audienceServiceMatrix.find(
    (item) =>
      item.audienceSlug === params.audience &&
      item.serviceSlug === params.service
  );

  const audience = audiences.find((item) => item.slug === params.audience);
  const service = services.find((item) => item.slug === params.service);

  if (!matrixItem || !audience || !service) {
    notFound();
  }

  return (
    <AudienceServicePageTemplate
      audience={audience}
      service={service}
      matrixItem={matrixItem}
    />
  );
}
```

---

# 9. Example Static Params for Local + Service Pages

Route:

```txt
app/service-areas/[location]/[service]/page.tsx
```

Example:

```tsx
import { notFound } from "next/navigation";
import { serviceAreas } from "@/data/serviceAreas";
import { services } from "@/data/services";
import { locationServiceMatrix } from "@/data/locationServiceMatrix";
import { LocationServicePageTemplate } from "@/templates/LocationServicePageTemplate";

export function generateStaticParams() {
  return locationServiceMatrix.map((item) => ({
    location: item.locationSlug,
    service: item.serviceSlug,
  }));
}

export default function LocationServicePage({
  params,
}: {
  params: { location: string; service: string };
}) {
  const matrixItem = locationServiceMatrix.find(
    (item) =>
      item.locationSlug === params.location &&
      item.serviceSlug === params.service
  );

  const location = serviceAreas.find((item) => item.slug === params.location);
  const service = services.find((item) => item.slug === params.service);

  if (!matrixItem || !location || !service) {
    notFound();
  }

  return (
    <LocationServicePageTemplate
      location={location}
      service={service}
      matrixItem={matrixItem}
    />
  );
}
```

---

# 10. Unsupported or Restricted Features

For static export, avoid anything that requires runtime server behavior.

Do not use:

```txt
API routes
Route handlers that require runtime server execution
Server actions
Dynamic server rendering
Runtime database queries
Runtime CMS fetches
Runtime authentication
Middleware that must run at request time
Dynamic redirects generated at request time
Image Optimization API
Draft mode
Preview mode
Runtime revalidation
```

Use static alternatives instead.

---

# 11. Static-Friendly Alternatives

## Instead of API Routes

Use:

```txt
Static data files
External form provider
Client-side form embed
Cloudflare Pages Functions, only if separately approved
```

## Instead of Server Actions

Use:

```txt
External form endpoint
CRM embed
GHL form embed
Static contact page with approved form integration
```

## Instead of Runtime CMS Fetching

Use:

```txt
Local data files
Markdown files
MDX files, if approved
Build-time generated content
```

## Instead of Runtime Image Optimization

Use:

```txt
Pre-optimized WebP images
SVG icons
Static images in public/
images.unoptimized: true
```

---

# 12. Image Handling Rules

Because this project uses static export, images must be handled carefully.

## Required Config

```ts
images: {
  unoptimized: true,
}
```

## Recommended Image Location

```txt
public/images/
```

Recommended folders:

```txt
public/images/brand/
public/images/og/
public/images/services/
public/images/audiences/
public/images/service-areas/
public/images/industries/
public/images/resources/
public/images/backgrounds/
```

## Recommended Image Format

Use:

```txt
.webp for most images
.svg for logos and simple icons
.jpg for photos only when appropriate
.png only when transparency or source quality requires it
```

## Image Naming Rule

Use lowercase, hyphenated, descriptive file names.

Good:

```txt
hanover-online-bookkeeping-services.webp
hanover-tax-preparation-services.webp
hanover-nationwide-accounting-services-og.jpg
```

Avoid:

```txt
IMG_001.jpg
Final Hero.png
tax image 2.webp
```

---

# 13. Link Handling Rules

Use internal links that match the static export route structure.

## Recommended

```tsx
import Link from "next/link";

<Link href="/services/online-bookkeeping">
  Online Bookkeeping Services
</Link>
```

With `trailingSlash: true`, Next.js will output clean static routes.

## Do Not Use

```txt
Hardcoded .html links
Broken relative paths
Links to routes that are not generated
Links to draft pages
Links to old URLs without redirect handling
```

---

# 14. Canonical URL Rules

Canonical URLs should use the final production domain.

Base URL:

```txt
https://www.hanoveraa.com
```

Canonical format:

```txt
https://www.hanoveraa.com/services/online-bookkeeping/
```

Use trailing slash if `trailingSlash: true`.

## Recommended Helper

```ts
export function buildCanonical(path: string) {
  const baseUrl = "https://www.hanoveraa.com";
  const cleanPath = path.endsWith("/") ? path : `${path}/`;
  return `${baseUrl}${cleanPath}`;
}
```

---

# 15. Metadata and Static Export

Every static route should generate metadata at build time.

Use:

```txt
generateMetadata
```

or static metadata exports where appropriate.

## Dynamic Metadata Rule

For dynamic pages, metadata must be generated from local data files.

Do not fetch metadata from a runtime API.

Example:

```tsx
export function generateMetadata({ params }: { params: { service: string } }) {
  const service = services.find((item) => item.slug === params.service);

  if (!service) {
    return {};
  }

  return {
    title: service.metaTitle,
    description: service.metaDescription,
    alternates: {
      canonical: buildCanonical(service.path),
    },
  };
}
```

---

# 16. Schema and Static Export

JSON-LD schema should be rendered during static build.

Use:

```txt
src/components/schema/JsonLd.tsx
src/lib/schema.ts
src/data/schema.ts
```

Schema should be generated from local data.

Do not generate schema from runtime APIs.

Every indexable page should include:

```txt
BreadcrumbList schema
Relevant page-specific schema
FAQPage schema when visible FAQs exist
```

---

# 17. Sitemap Strategy

For static export, the sitemap should be available at:

```txt
/sitemap.xml
```

Recommended file placement:

```txt
public/sitemap.xml
```

Or generate it before export using a script.

Recommended script:

```txt
scripts/generate-sitemap.ts
```

## Sitemap Must Include

```txt
Core pages
Service pages
Audience pages
Audience + service pages
Nationwide pages
Nationwide + service pages
Local service-area pages
Local + service pages
Industry pages
Resource pages
FAQ pages
```

## Sitemap Must Exclude

```txt
Draft pages
Noindex pages
404 page
Thank-you pages, if noindexed
Testing pages
```

---

# 18. Robots Strategy

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

Do not block important sections.

Do not block matrix pages if they are approved, unique, and indexable.

---

# 19. Redirect Strategy

For Cloudflare Pages static sites, use:

```txt
public/_redirects
```

Known redirect file content:

```txt
/accounting-services /services/accounting 301
/taxprep /services/tax-preparation 301
/aboutus /about 301
/contact-us-index /contact 301
/contact-us-form /contact 301
/our-offices /service-areas 301
```

The `_redirects` file should be copied into the final `out/` folder during build because it lives in `public/`.

---

# 20. Environment Variables

Use environment variables only when needed.

Recommended file for local development:

```txt
.env.local
```

Do not commit `.env.local`.

Potential variables:

```txt
NEXT_PUBLIC_SITE_URL=https://www.hanoveraa.com
NEXT_PUBLIC_GA_ID=
NEXT_PUBLIC_GTM_ID=
NEXT_PUBLIC_FORM_ENDPOINT=
```

Only use public variables for browser-safe values.

Do not expose secrets in `NEXT_PUBLIC_` variables.

---

# 21. Forms and Static Export

Forms need a static-compatible approach.

Do not rely on internal Next.js API routes unless Cloudflare Functions are explicitly approved and configured.

## Approved Static-Friendly Form Options

```txt
External CRM form embed
External form endpoint
GHL form embed
Cloudflare Pages Functions, if approved separately
mailto fallback, if approved
```

## Form Confirmation Required

Before launch, confirm:

```txt
Form provider
Recipient email
CRM destination
Required fields
Spam protection
Privacy notice
Thank-you page behavior
Tracking events
```

---

# 22. Analytics and Tracking

Analytics must be client-side compatible.

Potential tools:

```txt
Google Tag Manager
Google Analytics 4
Bing Webmaster Tools
Google Search Console
Microsoft Clarity, if approved
```

Add tracking scripts in a way that works with static export.

Do not add tracking IDs until approved.

Recommended placeholders:

```txt
NEXT_PUBLIC_GTM_ID=
NEXT_PUBLIC_GA_ID=
```

---

# 23. Static Export Build Checklist

Before deploying, run:

```txt
npm install
npm run typecheck
npm run build
```

Confirm:

```txt
out/ folder is generated.
Homepage exports correctly.
Core pages export correctly.
Dynamic service pages export correctly.
Audience pages export correctly.
Audience + service pages export correctly.
Nationwide pages export correctly.
Local service-area pages export correctly.
Local + service pages export correctly.
Industry pages export correctly.
Resource pages export correctly.
FAQ pages export correctly.
Images load correctly.
CSS loads correctly.
Navigation links work.
404 page works.
robots.txt exists.
sitemap.xml exists.
_redirects exists, if used.
```

---

# 24. Common Static Export Mistakes

Avoid these mistakes:

```txt
Forgetting output: "export"
Forgetting images.unoptimized: true
Using API routes for forms
Using server actions
Using runtime-only route handlers
Using dynamic routes without generateStaticParams
Using runtime CMS fetching
Forgetting sitemap.xml
Forgetting robots.txt
Forgetting _redirects
Using broken internal links
Using old URL paths without redirects
Using canonical URLs without trailing slashes when trailingSlash is true
```

---

# 25. Data-Driven Static Page Generation

The Hanover build should generate pages from local data files.

Data files:

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

These files should power:

```txt
generateStaticParams
Metadata
Schema
Sitemap
Internal links
Navigation
Related pages
Page templates
```

---

# 26. Static Export and Large Page Count

The full build may include hundreds of static pages.

Expected page groups:

```txt
Core pages
Hub pages
24 core service pages
8 audience pages
103 audience + service pages
17 nationwide + service pages
10 local service-area pages
170 local + service pages
Industry pages
Resource pages
FAQ pages
```

This is appropriate for static export if:

```txt
Routes are generated at build time.
Content is stored locally or generated at build time.
The build remains performant.
No runtime server features are required.
```

---

# 27. Type Safety Requirements

Use TypeScript types for all major data structures.

Recommended types:

```txt
Service
Audience
AudienceServicePage
ServiceArea
LocationServicePage
Industry
ResourceCategory
ResourceArticle
FAQCategory
PageMetadata
```

Invalid route data should fail during development or route validation.

---

# 28. Optional Validation Scripts

For a large static site, add validation scripts.

Recommended scripts:

```txt
scripts/validate-routes.ts
scripts/validate-metadata.ts
scripts/validate-schema.ts
scripts/validate-internal-links.ts
scripts/generate-sitemap.ts
```

Recommended `package.json` scripts:

```json
{
  "scripts": {
    "validate:routes": "tsx scripts/validate-routes.ts",
    "validate:metadata": "tsx scripts/validate-metadata.ts",
    "validate:schema": "tsx scripts/validate-schema.ts",
    "validate:links": "tsx scripts/validate-internal-links.ts",
    "generate:sitemap": "tsx scripts/generate-sitemap.ts"
  }
}
```

Optional dependency:

```txt
tsx
```

---

# 29. Deployment Expectations

Cloudflare Pages should receive the `out/` folder.

Cloudflare Pages settings:

```txt
Framework preset: Next.js or None/static, depending on Cloudflare setup
Build command: npm run build
Output directory: out
Node version: current supported LTS
Root directory: project root
```

If Cloudflare auto-detects a Next.js server deployment mode, ensure the project is still exporting static output to `out`.

---

# 30. Static Export QA Checklist

Before handing off to Cloudflare deployment, confirm:

```txt
next.config.ts has output: "export".
next.config.ts has trailingSlash: true.
next.config.ts has images.unoptimized: true.
npm run build completes successfully.
out/ folder exists.
out/index.html exists.
Dynamic route pages exist in out/.
CSS and JavaScript assets load correctly.
Images load from public paths.
Navigation works on exported pages.
Direct URL reloads work.
404 page works.
sitemap.xml is available.
robots.txt is available.
_redirects file is available if used.
No server-only code is required.
No API routes are required.
No server actions are used.
No runtime CMS fetch is required.
Canonical URLs use production domain.
Metadata is generated.
Schema is rendered.
```

---

# 31. Final Static Export Direction

The Hanover site must remain a static, data-driven Next.js build that exports to:

```txt
out
```

The build should support:

```txt
Cloudflare Pages deployment
Fast static pages
Large route matrix generation
SEO
GEO
AEO
Local service-area visibility
Nationwide service visibility
LLM search visibility
Structured data
Sitemap generation
Conversion tracking
Clean internal linking
```

Do not add runtime server features unless the deployment architecture is intentionally changed and approved.
