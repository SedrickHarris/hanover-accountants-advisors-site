# Cloudflare Pages Deployment

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the Cloudflare Pages deployment strategy for the Hanover Accountants & Advisors website rebuild.

The site will be built as a static Next.js export and deployed to Cloudflare Pages using the generated `/out` directory.

The deployment strategy must support:

* Static Next.js hosting
* Cloudflare Pages
* GitHub deployment
* Preview deployments
* Production deployments
* Custom domain setup
* Redirects
* Robots.txt
* Sitemap.xml
* Environment variables
* Analytics and tracking
* SEO launch readiness
* Google Search Console
* Bing Webmaster Tools
* Apple Search visibility
* Performance
* Security
* Conversion tracking
* Long-term maintainability

---

# 1. Deployment Summary

The Hanover website will be deployed as a static site.

## Stack

```txt
Next.js App Router
TypeScript
Static export
GitHub
Cloudflare Pages
Cloudflare DNS
Cloudflare redirects
Cloudflare preview deployments
```

## Build Output

```txt
out
```

## Production Domain

```txt
https://www.hanoveraa.com
```

Confirm the final production domain before launch.

---

# 2. Cloudflare Pages Build Settings

Use these settings in Cloudflare Pages.

```txt
Project name: hanover-aa-site
Production branch: main
Build command: npm run build
Build output directory: out
Root directory: /
Node.js version: current supported LTS
```

> ⚠️ **Naming note:** The repo actually in use is `hanover-accountants-advisors-site`,
> not `hanover-aa-site`. Use the real repo name when connecting Cloudflare Pages to Git,
> or rename the repo first.

## Framework Preset

Use one of the following depending on Cloudflare detection:

```txt
Framework preset: Next.js
```

or:

```txt
Framework preset: None
```

Because this project is a static export, the critical setting is:

```txt
Output directory: out
```

---

# 3. Required Next.js Configuration

The project must include static export configuration.

File:

```txt
next.config.ts
```

Required configuration:

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

## Why This Matters

```txt
output: "export" generates static files.
trailingSlash: true supports folder-style static routes.
images.unoptimized: true avoids runtime image optimization.
Cloudflare Pages serves the static files from out.
```

---

# 4. GitHub Repository Setup

Recommended repository:

```txt
SedrickHarris/hanover-aa-site
```

Recommended remote:

```txt
https://github.com/SedrickHarris/hanover-aa-site.git
```

> ⚠️ **Naming note:** The repo actually created and connected is
> `SedrickHarris/hanover-accountants-advisors-site`
> (https://github.com/SedrickHarris/hanover-accountants-advisors-site.git).

## Required Branch

```txt
main
```

## Initial Git Commands

```bash
git init
git add -A
git commit -m "Initial Hanover Accountants and Advisors site scaffold"
git branch -M main
git remote add origin https://github.com/SedrickHarris/hanover-aa-site.git
git push -u origin main
```

Only use these commands after the local project is ready and the remote repository exists.

---

# 5. Recommended Local Project Path

Use:

```txt
C:\Users\Welcome\Desktop\client-sites\hanover-aa-site
```

Local project should contain:

```txt
README.md
CLAUDE.md
docs/
app/
src/
public/
next.config.ts
package.json
```

---

# 6. Cloudflare Pages Project Creation

## Step 1: Create Pages Project

In Cloudflare:

```txt
Workers & Pages
Create application
Pages
Connect to Git
Select GitHub
Select repository: hanover-aa-site
```

## Step 2: Configure Build

Use:

```txt
Production branch: main
Build command: npm run build
Output directory: out
Root directory: /
```

## Step 3: Deploy

Cloudflare will install dependencies, run the build command, and publish the `out` folder.

---

# 7. Preview Deployment Strategy

Cloudflare Pages can create preview deployments for non-production branches and pull requests.

Use preview deployments for:

```txt
Design review
Client review
Content QA
Metadata QA
Schema QA
Mobile QA
Redirect QA
Internal link QA
Performance review
```

## Recommended Branch Pattern

```txt
main
staging
feature/homepage
feature/services
feature/service-areas
feature/resources
```

## Preview Rule

Do not connect final production domain until the site passes QA.

---

# 8. Production Deployment Strategy

Production should deploy from:

```txt
main
```

Before merging into `main`, verify:

```txt
Build passes.
Routes generate.
Metadata is complete.
Schema is valid.
Robots.txt is correct.
Sitemap.xml is correct.
Redirects are correct.
Forms are tested.
Tracking is approved.
No fake claims are present.
No fake local office language is present.
```

---

# 9. Custom Domain Setup

Recommended production domain:

```txt
www.hanoveraa.com
```

Recommended apex domain redirect:

```txt
hanoveraa.com -> www.hanoveraa.com
```

## Cloudflare Custom Domain Steps

In the Pages project:

```txt
Go to Custom domains.
Add www.hanoveraa.com.
Verify DNS.
Add hanoveraa.com if needed.
Configure apex to redirect to www.
```

## Domain Rule

Choose one canonical domain.

Recommended canonical domain:

```txt
https://www.hanoveraa.com
```

Use this consistently for:

```txt
Canonical URLs
Sitemap URLs
Open Graph URLs
Schema URLs
Google Search Console
Bing Webmaster Tools
Apple Business Connect
Google Business Profile
```

---

# 10. DNS Strategy

If DNS is managed in Cloudflare, connect the Pages project through Cloudflare's custom domain workflow.

Before launch, confirm:

```txt
DNS host
Current A records
Current CNAME records
Current MX records
Current TXT records
Email provider records
SPF
DKIM
DMARC
Existing subdomains
Client portal subdomain, if any
```

## Important Email Rule

Do not change MX, SPF, DKIM, or DMARC records unless email migration is part of the project.

Website launch should not break email.

---

# 11. SSL and HTTPS

Cloudflare should serve the site over HTTPS.

Confirm:

```txt
HTTPS works on www.hanoveraa.com.
HTTP redirects to HTTPS.
Apex domain redirects to canonical www domain.
No mixed content warnings appear.
All internal links use HTTPS canonical URLs.
```

---

# 12. Redirect Strategy

Use Cloudflare Pages `_redirects`.

File location:

```txt
public/_redirects
```

Because the file is in `public/`, it should be copied into the `out/` folder during build.

## Known Redirects

```txt
/accounting-services /services/accounting 301
/taxprep /services/tax-preparation 301
/aboutus /about 301
/contact-us-index /contact 301
/contact-us-form /contact 301
/our-offices /service-areas 301
```

## Redirect Rules

Use 301 redirects for permanent old-to-new URL changes.

Do not redirect everything to the homepage.

Each old URL should redirect to the closest relevant new page.

## Redirect QA

Before launch, test:

```txt
/accounting-services
/taxprep
/aboutus
/contact-us-index
/contact-us-form
/our-offices
```

Confirm each redirects to the correct new destination.

---

# 13. Apex to WWW Redirect

Recommended canonical domain:

```txt
www.hanoveraa.com
```

Redirect:

```txt
hanoveraa.com/* -> https://www.hanoveraa.com/$1
```

This can be handled with Cloudflare Redirect Rules or Bulk Redirects.

Do not rely only on canonical tags for domain consolidation.

---

# 14. Pages.dev Preview Domain

Cloudflare Pages creates a default preview domain:

```txt
hanover-aa-site.pages.dev
```

Use this for:

```txt
Internal review
Client review
Prelaunch QA
Build testing
```

After production launch, decide whether to redirect the `.pages.dev` domain to the canonical custom domain.

Recommended:

```txt
Redirect pages.dev preview domain to www.hanoveraa.com after production launch, if the client does not need preview access.
```

If ongoing preview access is useful, keep preview deployments available but do not promote `.pages.dev` as the public URL.

---

# 15. Environment Variables

Environment variables are managed in the Cloudflare Pages project settings.

Potential variables:

```txt
NEXT_PUBLIC_SITE_URL=https://www.hanoveraa.com
NEXT_PUBLIC_GA_ID=
NEXT_PUBLIC_GTM_ID=
NEXT_PUBLIC_FORM_ENDPOINT=
```

## Environment Variable Rules

Use `NEXT_PUBLIC_` only for values that are safe to expose in the browser.

Do not store secrets in public variables.

Do not commit `.env.local`.

Do not add tracking IDs until approved.

## Local Environment File

Use:

```txt
.env.local
```

Add to `.gitignore`:

```txt
.env
.env.local
.env.production
```

---

# 16. Forms Deployment Strategy

Because this is a static export, forms must use a static-compatible approach.

Approved options:

```txt
External CRM form embed
External form endpoint
GHL form embed
Cloudflare Pages Functions, if separately approved
Mailto fallback, if approved
```

Do not rely on internal Next.js API routes for production forms unless the architecture changes.

## Form Confirmation Required

Before launch, confirm:

```txt
Form provider
Destination email
CRM destination
Required fields
Spam protection
Privacy text
Thank-you behavior
Conversion tracking
```

## Form QA

Test:

```txt
Contact form
Schedule consultation form
Get started form
Client portal link
Required fields
Error states
Success state
Mobile usability
Tracking events
```

---

# 17. Analytics and Tracking

Do not install tracking until approved.

Potential tools:

```txt
Google Tag Manager
Google Analytics 4
Google Search Console
Bing Webmaster Tools
Microsoft Clarity, if approved
Apple Business Connect links, if applicable
```

## Recommended Tracking Setup

Use Google Tag Manager if tracking will include multiple events.

Potential events:

```txt
Click to call
Email click
Schedule consultation click
Contact form submit
Client portal click
Get started click
Service page CTA click
Local page CTA click
Resource CTA click
```

## Tracking Rule

Do not hardcode temporary tracking IDs into the codebase.

Use environment variables or approved constants.

---

# 18. Google Search Console Setup

After launch, add and verify:

```txt
https://www.hanoveraa.com
```

Recommended property type:

```txt
Domain property, if DNS access is available
```

or:

```txt
URL-prefix property, if DNS verification is not available
```

Submit:

```txt
https://www.hanoveraa.com/sitemap.xml
```

## GSC QA

Check:

```txt
Indexing status
Sitemap discovered
Canonical URLs
Mobile usability
Page indexing errors
404 errors
Redirect errors
Duplicate content warnings
Rich result eligibility
```

---

# 19. Bing Webmaster Tools Setup

After launch, add:

```txt
https://www.hanoveraa.com
```

Submit:

```txt
https://www.hanoveraa.com/sitemap.xml
```

Use Bing Webmaster Tools for:

```txt
Indexing review
Sitemap submission
Crawl errors
SEO reports
Bing visibility
Microsoft ecosystem visibility
```

---

# 20. Apple Search and Apple Business Connect Alignment

If Hanover has verified business locations, align website URLs with Apple Business Connect.

Confirm before launch:

```txt
Verified business name
Verified address
Verified phone
Verified website URL
Verified service categories
Verified office locations
```

Do not create Apple location links or local claims for unverified service areas.

---

# 21. Google Business Profile Alignment

For verified office locations, align website URLs with Google Business Profile.

Potential GBP URLs:

```txt
Homepage: https://www.hanoveraa.com/
Atlanta service area page: https://www.hanoveraa.com/service-areas/atlanta-ga/
Alexandria page, only if confirmed: https://www.hanoveraa.com/service-areas/alexandria-va/
```

## GBP Rule

Do not connect unverified service-area pages to fake GBP locations.

Do not imply physical offices in nearby markets unless confirmed.

---

# 22. Robots.txt

File:

```txt
public/robots.txt
```

Recommended launch version:

```txt
User-agent: *
Allow: /

Sitemap: https://www.hanoveraa.com/sitemap.xml
```

## Robots QA

Confirm:

```txt
robots.txt is available at /robots.txt.
Sitemap URL is correct.
Important sections are not blocked.
Preview or staging URLs are not accidentally indexed if they should stay private.
```

---

# 23. Sitemap.xml

File:

```txt
public/sitemap.xml
```

or generated by:

```txt
scripts/generate-sitemap.ts
```

Final URL:

```txt
https://www.hanoveraa.com/sitemap.xml
```

## Sitemap Should Include

```txt
Core pages
Hub pages
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

## Sitemap Should Exclude

```txt
404 page
Noindex pages
Draft pages
Test pages
Thank-you pages, if noindexed
```

---

# 24. HTML Sitemap

The site should include a human-readable sitemap:

```txt
/sitemap
```

The HTML sitemap should group pages by:

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

This helps users, search engines, and QA reviewers find the full page set.

---

# 25. Build and Deployment Commands

## Local Development

```bash
npm install
npm run dev
```

## Type Check

```bash
npm run typecheck
```

## Production Build

```bash
npm run build
```

## Expected Build Result

```txt
out/
```

## Cloudflare Build Command

```txt
npm run build
```

## Cloudflare Output Directory

```txt
out
```

---

# 26. Pre-Deployment Local QA

Before pushing to GitHub or triggering Cloudflare production deploy, run:

```bash
npm run typecheck
npm run build
```

Then verify:

```txt
out/ folder exists.
out/index.html exists.
Core routes export.
Dynamic routes export.
Images load.
Styles load.
Navigation works.
Forms render.
robots.txt exists.
sitemap.xml exists.
_redirects exists, if used.
No server runtime is required.
```

---

# 27. Cloudflare Deployment QA

After Cloudflare deploys, test the Pages URL.

Check:

```txt
Homepage loads.
Core pages load.
Service pages load.
Audience pages load.
Audience + service pages load.
Nationwide pages load.
Local service-area pages load.
Local + service pages load.
Industry pages load.
Resource pages load.
FAQ pages load.
404 page works.
CSS loads.
JavaScript loads.
Images load.
Mobile navigation works.
Forms work or show approved placeholder state.
Redirects work.
Sitemap is accessible.
Robots.txt is accessible.
```

---

# 28. Production Launch QA

After connecting the custom domain, test:

```txt
https://www.hanoveraa.com
https://hanoveraa.com
http://www.hanoveraa.com
http://hanoveraa.com
```

Expected behavior:

```txt
All versions resolve or redirect correctly to https://www.hanoveraa.com.
No SSL errors.
No mixed content warnings.
No redirect loops.
No duplicate canonical domain issues.
```

---

# 29. Page Speed and Performance QA

Test after deployment.

Recommended tools:

```txt
PageSpeed Insights
Lighthouse
WebPageTest, optional
Cloudflare Analytics
Chrome DevTools
```

Review:

```txt
Largest Contentful Paint
Cumulative Layout Shift
Interaction to Next Paint
Image sizes
Unused JavaScript
Font loading
Mobile performance
Desktop performance
```

## Static Site Performance Rules

Use:

```txt
Compressed images
WebP where appropriate
Minimal third-party scripts
Static assets
Clean CSS
Limited tracking scripts
Accessible image dimensions
```

Avoid:

```txt
Oversized hero images
Too many third-party scripts
Layout shifts
Unoptimized fonts
Unused JavaScript
```

---

# 30. Security and Platform Settings

Cloudflare can provide performance and security features.

Recommended review items:

```txt
SSL/TLS mode
Always Use HTTPS
Automatic HTTPS Rewrites
WAF settings, if available
Bot protection, if available
Security headers, if configured
Cache settings
Page Shield, if available and approved
```

Do not enable aggressive settings that break forms, scripts, or client portal links.

---

# 31. Caching Strategy

Cloudflare Pages will serve static assets efficiently.

Recommended:

```txt
Use hashed Next.js assets for cache-friendly static files.
Keep images in public/images with optimized sizes.
Avoid changing filenames unless images change.
Use Cloudflare default caching unless specific issues arise.
```

After launch, clear cache only if needed.

---

# 32. External Links QA

Before launch, confirm external links:

```txt
Client portal
Social profiles, if used
Google Business Profile, if linked
Apple Business Connect, if linked
Scheduling tool, if external
Form provider
Privacy or legal links, if external
```

Do not link to unapproved profiles.

---

# 33. Client Portal Deployment Rule

The site includes:

```txt
/client-portal
```

This page should either:

```txt
Link to the verified external client portal.
Explain how existing clients access the portal.
Provide a CTA to contact Hanover if access is needed.
```

Before launch, confirm:

```txt
Final client portal URL
Whether the portal opens in same tab or new tab
Any required disclaimer text
Any approved support instructions
```

Do not invent portal features.

---

# 34. Deployment Rollback Plan

Cloudflare Pages keeps previous deployments.

If production has a critical issue:

```txt
Pause changes.
Identify the last known good deployment.
Rollback to the previous successful deployment.
Fix the issue in GitHub.
Redeploy from main after QA.
```

Common rollback triggers:

```txt
Broken homepage
Broken navigation
Broken CSS
Broken forms
Incorrect DNS
Redirect loop
Wrong canonical domain
Major content error
```

---

# 35. Launch Checklist

Before production launch:

```txt
Client approves design.
Client approves content.
Client confirms contact details.
Client confirms office details.
Client confirms Richmond vs Alexandria language.
Client confirms client portal URL.
Client confirms form destination.
Client confirms tracking IDs.
Client confirms legal pages.
All routes build.
All pages have metadata.
All pages have schema where appropriate.
Sitemap is generated.
Robots.txt is correct.
Redirects are configured.
Custom domain is ready.
DNS records are reviewed.
Email records are protected.
Cloudflare Pages deploys successfully.
```

---

# 36. Post-Launch Checklist

After launch:

```txt
Verify live homepage.
Verify top service pages.
Verify contact page.
Verify schedule consultation page.
Verify forms.
Verify phone links.
Verify email links.
Verify client portal link.
Verify sitemap.xml.
Verify robots.txt.
Verify redirects.
Verify canonical domain.
Submit sitemap to Google Search Console.
Submit sitemap to Bing Webmaster Tools.
Inspect key URLs in Google Search Console.
Check Cloudflare analytics.
Check PageSpeed Insights.
Monitor 404s and redirect errors.
```

---

# 37. Deployment Troubleshooting

## Issue: Cloudflare Says Output Directory Not Found

Check:

```txt
next.config.ts includes output: "export".
Build command is npm run build.
Build output directory is out.
The build completes locally.
No custom script deletes out.
```

## Issue: Images Do Not Load

Check:

```txt
Images are in public/images.
Image paths start with /images/.
next.config.ts includes images.unoptimized: true.
File names are lowercase and correct.
```

## Issue: Dynamic Pages Missing

Check:

```txt
generateStaticParams exists.
Matrix data includes the route.
Slug names match exactly.
Build logs do not show route errors.
Invalid pages use notFound().
```

## Issue: Redirects Do Not Work

Check:

```txt
public/_redirects exists.
_redirects has no file extension.
_redirects is copied to out.
Redirect syntax is correct.
Cloudflare deployment picked up the latest build.
```

## Issue: Canonical URLs Are Wrong

Check:

```txt
NEXT_PUBLIC_SITE_URL is correct, if used.
Metadata helper uses https://www.hanoveraa.com.
Trailing slash behavior is consistent.
Preview URLs are not used as production canonicals.
```

---

# 38. Deployment File Checklist

The final repository should include:

```txt
next.config.ts
package.json
README.md
CLAUDE.md
docs/
app/
src/
public/robots.txt
public/sitemap.xml
public/_redirects
public/images/
```

The final repository should not include:

```txt
node_modules/
.next/
out/
.env
.env.local
.env.production
Private credentials
Client secrets
```

---

# 39. Final Deployment Direction

The Hanover site should deploy to Cloudflare Pages as a static Next.js export.

Final deployment settings:

```txt
Build command: npm run build
Output directory: out
Production branch: main
Canonical domain: https://www.hanoveraa.com
```

The final deployment must preserve:

```txt
Static export compatibility
SEO metadata
Schema markup
Sitemap access
Robots access
Redirects
Mobile navigation
Forms
Client portal access
Local service-area accuracy
Nationwide positioning
Fast page performance
Conversion tracking readiness
```

Do not add server-side dependencies unless the architecture is intentionally changed and approved.
