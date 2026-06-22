# Prelaunch Checklist

## Project

Hanover Accountants & Advisors Website Rebuild

## Purpose of This Document

This document defines the prelaunch checklist for the Hanover Accountants & Advisors website rebuild.

The checklist should be used before the site is deployed to production on Cloudflare Pages.

The purpose is to confirm that the website is:

* Technically ready
* Content-approved
* Static-export compatible
* SEO-ready
* GEO-ready
* AEO-ready
* LLM-search-ready
* Metadata-complete
* Schema-complete
* Internally linked
* Accessible
* Mobile-friendly
* Conversion-ready
* Accurate
* Free of unsupported claims
* Ready for Google Search Console and Bing Webmaster Tools

This checklist should be completed before connecting the final production domain.

---

# 1. Project Documentation Checklist

Confirm all project documents exist in the `docs/` folder.

```txt
README.md
CLAUDE.md
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
```

## Documentation QA

Confirm:

```txt
All documents are saved.
All documents match the approved project direction.
The Claude Code handoff document includes the verbatim content lock.
The do-not-invent document is included.
The Richmond and Alexandria location issue is clearly flagged.
Static export requirements are included.
Cloudflare Pages /out deployment instructions are included.
```

---

# 2. Claude Project Workflow Checklist

Confirm the workflow was followed.

```txt
Claude Project researched each page or page group.
Claude Project created approved page strategy.
Claude Project created approved copy.
Claude Project created approved metadata.
Claude Project created approved schema guidance.
Claude Project created approved FAQs.
Claude Project created approved internal links.
Claude Project created approved build prompts for Claude Code.
Claude Code built from approved prompts only.
Claude Code did not rewrite approved content.
```

## Content Lock QA

Confirm Claude Code did not change:

```txt
Headlines
Subheadings
Hero copy
Body copy
Direct answers
FAQ questions
FAQ answers
CTA labels
Metadata titles
Meta descriptions
Schema text fields
Alt text
Navigation labels
Internal link anchor text
Legal copy
Disclaimers
```

---

# 3. Repository Checklist

Confirm the repository is ready.

```txt
Git repository exists.
Remote repository exists.
Correct GitHub remote is connected.
Main branch exists.
Latest work is committed.
No uncommitted launch-critical changes remain.
Repository does not include private credentials.
Repository does not include environment files.
Repository does not include node_modules.
Repository does not include .next.
Repository does not include out.
```

## Recommended Repository

```txt
SedrickHarris/hanover-aa-site
```

> ⚠️ **Naming note:** The repo actually in use is
> `SedrickHarris/hanover-accountants-advisors-site`, and the local folder is
> `C:\Users\Welcome\Desktop\client-sites\hanover-accountants-advisors-site`.

## Recommended Local Folder

```txt
C:\Users\Welcome\Desktop\client-sites\hanover-aa-site
```

---

# 4. Static Export Checklist

Confirm `next.config.ts` includes:

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

Confirm:

```txt
Static export is enabled.
Trailing slash behavior is consistent.
Images are unoptimized for static export.
No server runtime is required.
No API routes are required.
No server actions are used.
No runtime CMS fetches are required.
No runtime database calls are required.
The build generates an out folder.
```

---

# 5. Build Command Checklist

Run locally:

```bash
npm install
npm run typecheck
npm run build
```

Confirm:

```txt
Typecheck passes.
Build passes.
No blocking TypeScript errors.
No blocking lint errors.
out/ folder is generated.
out/index.html exists.
Static pages are generated.
Dynamic routes are generated.
No runtime server errors appear.
```

---

# 6. Cloudflare Pages Checklist

Confirm Cloudflare Pages settings.

```txt
Project name: hanover-aa-site
Production branch: main
Build command: npm run build
Output directory: out
Root directory: /
Node.js version: current supported LTS
```

Confirm:

```txt
Cloudflare Pages project exists.
GitHub repository is connected.
Preview deployment works.
Production deployment is not connected to final domain until QA is complete.
Output directory is set to out.
Build logs show successful export.
```

---

# 7. Domain Checklist

Confirm the final canonical domain.

Recommended:

```txt
https://www.hanoveraa.com
```

Confirm:

```txt
Canonical domain is final.
WWW vs apex decision is final.
HTTP redirects to HTTPS.
Apex redirects to WWW, if WWW is canonical.
No redirect loops exist.
No duplicate canonical domain issue exists.
Cloudflare SSL is active.
No mixed content warnings appear.
```

---

# 8. DNS Checklist

Before launch, confirm:

```txt
DNS host is known.
Existing DNS records are reviewed.
A records are reviewed.
CNAME records are reviewed.
MX records are protected.
SPF records are protected.
DKIM records are protected.
DMARC records are protected.
Existing subdomains are protected.
Client portal subdomain, if any, is protected.
```

## Email Safety Rule

Do not change email-related records unless email migration is part of the project.

Protect:

```txt
MX
SPF
DKIM
DMARC
Mail-related CNAME records
Mail-related TXT records
```

---

# 9. Route Checklist

Confirm these core routes exist and load.

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

Confirm these hubs exist and load.

```txt
/services
/services/accounting
/services/tax
/services/advisory
/who-we-help
/service-areas
/service-areas/nationwide
/industries
/resources
/faqs
```

Confirm dynamic route groups generate correctly.

```txt
/services/[service]
/who-we-help/[audience]
/who-we-help/[audience]/[service]
/service-areas/nationwide/[service]
/service-areas/[location]
/service-areas/[location]/[service]
/industries/[industry]
/resources/[category]
/resources/[category]/[slug]
/faqs/[category]
```

---

# 10. Dynamic Route Checklist

Confirm every dynamic route uses `generateStaticParams`.

```txt
app/services/[service]/page.tsx
app/who-we-help/[audience]/page.tsx
app/who-we-help/[audience]/[service]/page.tsx
app/service-areas/nationwide/[service]/page.tsx
app/service-areas/[location]/page.tsx
app/service-areas/[location]/[service]/page.tsx
app/industries/[industry]/page.tsx
app/resources/[category]/page.tsx
app/resources/[category]/[slug]/page.tsx
app/faqs/[category]/page.tsx
```

Confirm:

```txt
Approved slugs generate.
Invalid slugs call notFound().
No unapproved slugs generate.
No accidental duplicate routes exist.
No broken route paths exist.
```

---

# 11. Content Accuracy Checklist

Confirm the site does not invent:

```txt
Credentials
Licenses
Certifications
Team members
Awards
Reviews
Testimonials
Case studies
Client results
Pricing
Packages
Office addresses
Business hours
Physical offices
Guarantees
Tax outcomes
Audit protection claims
Software names
State-specific tax guarantees
Local rankings
```

Confirm:

```txt
All content matches approved Claude Project build prompts.
No Claude Code-generated copy was added without approval.
No unapproved claims appear.
No fake local office language appears.
No fake review or rating language appears.
No guaranteed tax outcome language appears.
No personalized tax advice appears.
```

---

# 12. Richmond and Alexandria Checklist

Before launch, confirm the Virginia location issue is resolved.

The source site references a Richmond, Virginia office, but the displayed address is in Alexandria, Virginia.

Confirm with the client:

```txt
Is Alexandria, VA a physical office?
Is Richmond, VA a physical office?
Is Richmond, VA only a service area?
Which Virginia address should be used publicly?
Which Virginia phone number should be used publicly?
Which Virginia location should be used for schema?
Which Virginia location should connect to Google Business Profile?
Which Virginia location should connect to Apple Business Connect?
```

Until confirmed, avoid:

```txt
Visit our Richmond office.
Our Richmond office is located at an Alexandria address.
LocalBusiness schema for Richmond.
Fake Richmond office details.
Fake Alexandria office details.
```

Use safe language:

```txt
Hanover serves clients in Richmond, VA through secure online accounting, tax, bookkeeping, payroll, and advisory workflows.
```

---

# 13. Local Page Checklist

For each local service-area page, confirm:

```txt
Page has unique local content.
Page uses service-area language unless office is verified.
Page does not claim a fake physical office.
Page does not list fake business hours.
Page does not use fake coordinates.
Page links to related local service pages.
Page links to nearby service areas.
Page links to nationwide service page.
Page includes a CTA.
Page includes FAQs where appropriate.
Page has metadata.
Page has schema.
```

Local service-area pages:

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

---

# 14. Local + Service Page Checklist

For each local + service page, confirm:

```txt
Page has unique city + service content.
Page has a city + service H1.
Page has unique metadata.
Page has a direct answer section.
Page links to parent service-area page.
Page links to core service page.
Page links to nationwide + service page.
Page links to related local service pages.
Page links to nearby service areas.
Page includes approved FAQs.
Page includes a CTA.
Page does not use fake office language.
Page does not use unapproved LocalBusiness schema.
```

Confirm all approved local + service pages are generated.

Target:

```txt
170 local + service pages
```

---

# 15. Nationwide Page Checklist

Confirm:

```txt
/service-areas/nationwide exists.
/service-areas/nationwide/[service] pages exist.
Nationwide pages emphasize online service delivery.
Nationwide pages do not claim offices nationwide.
Nationwide pages include secure workflow language.
Nationwide pages link to relevant services.
Nationwide pages link to relevant audiences.
Nationwide pages include CTAs.
Nationwide pages include metadata.
Nationwide pages include schema.
```

Target:

```txt
17 nationwide + service pages
```

---

# 16. Audience Page Checklist

Confirm audience pages exist.

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

Confirm each audience page:

```txt
Has unique audience-specific content.
Links to recommended services.
Links to audience + service pages.
Includes FAQs.
Includes CTA.
Has unique metadata.
Has schema.
Does not overstate unsupported claims.
```

---

# 17. Audience + Service Checklist

Confirm all approved audience + service pages are generated.

Target:

```txt
103 audience + service pages
```

Confirm each page:

```txt
Has unique audience + service content.
Has a specific H1.
Has approved metadata.
Has a direct answer section.
Links to parent audience page.
Links to core service page.
Links to relevant services.
Links to relevant resources.
Includes FAQs.
Includes CTA.
Uses approved copy verbatim.
Does not contain thin duplicate copy.
```

---

# 18. Service Page Checklist

Confirm all core service pages exist.

Target:

```txt
24 core service pages
```

Confirm each service page:

```txt
Has unique service content.
Has one H1.
Has approved metadata.
Has a direct answer section.
Has service includes section.
Has common problems solved section.
Has secure online workflow section.
Has related services.
Has related audiences.
Has related service areas.
Has FAQs.
Has CTA.
Has Service schema.
Has BreadcrumbList schema.
Has FAQPage schema when FAQs are visible.
```

---

# 19. Industry Page Checklist

Confirm industry pages exist.

```txt
/industries/agriculture
/industries/construction
/industries/design-firms
/industries/food-processing
/industries/professional-services
/industries/textile-businesses
```

Confirm each industry page:

```txt
Has unique industry-specific content.
Does not overstate specialization.
Does not invent industry-specific client results.
Links to relevant services.
Links to relevant resources.
Includes FAQs.
Includes CTA.
Has metadata.
Has schema.
```

---

# 20. Resource Page Checklist

Confirm resource structure exists.

```txt
/resources
/resources/[category]
/resources/[category]/[slug]
```

Confirm each resource article:

```txt
Has approved article copy.
Uses plain-English educational content.
Avoids personalized tax advice.
Links to relevant service pages.
Links to relevant audience pages where appropriate.
Links to related resources.
Includes CTA.
Has Article schema.
Has FAQPage schema only if visible FAQs exist.
Has unique metadata.
```

---

# 21. FAQ Page Checklist

Confirm FAQ pages exist.

```txt
/faqs
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

Confirm:

```txt
FAQ questions are visible.
FAQ answers are visible.
FAQ schema only marks up visible FAQs.
FAQ answers are not rewritten by Claude Code.
FAQ pages link to relevant services.
FAQ pages link to consultation CTA.
FAQ pages have metadata.
```

---

# 22. Metadata Checklist

Every indexable page should have:

```txt
Unique title tag
Unique meta description
Canonical URL
Open Graph title
Open Graph description
Open Graph image
Robots index, follow
One H1
```

Check for:

```txt
Missing title tags
Duplicate title tags
Missing meta descriptions
Duplicate meta descriptions
Wrong canonical URLs
Preview domain in canonical URLs
Missing OG metadata
Wrong robots directives
Multiple H1s
Missing H1s
```

Canonical base:

```txt
https://www.hanoveraa.com
```

---

# 23. Schema Checklist

Confirm schema is accurate and visible-content-aligned.

Use:

```txt
Organization
WebSite
BreadcrumbList
Service
FAQPage
Article
CollectionPage
LocalBusiness only for verified physical offices
```

Do not use:

```txt
Fake Review schema
Fake AggregateRating schema
Fake Offer schema
Fake pricing
Fake LocalBusiness schema
Fake business hours
Fake coordinates
Fake awards
Fake credentials
```

Confirm:

```txt
Breadcrumb schema matches visible breadcrumbs.
Service schema matches visible service content.
FAQPage schema only includes visible FAQs.
Article schema only appears on resource articles.
LocalBusiness schema only appears on verified office pages.
Organization schema uses verified business details.
No conflicting schema entities exist.
```

---

# 24. Internal Linking Checklist

Confirm every major page has internal links.

Check:

```txt
Service pages link to related services.
Service pages link to related audiences.
Service pages link to nationwide service pages.
Service pages link to priority service-area pages.
Audience pages link to relevant services.
Audience + service pages link to parent audience and core service.
Local pages link to nearby service areas.
Local + service pages link to parent location, core service, and nationwide page.
Resource pages link to services and related resources.
FAQ pages link to relevant services.
CTAs link to approved destinations.
```

Confirm no internal links are broken.

---

# 25. Navigation Checklist

Confirm main navigation uses approved labels:

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

Confirm:

```txt
Navigation labels were not changed by Claude Code.
Main nav works on desktop.
Mobile nav works.
Dropdown links work.
Footer links work.
CTA links work.
Current page states work if implemented.
Keyboard navigation works.
```

---

# 26. CTA Checklist

Approved CTA labels:

```txt
Schedule a Consultation
Request a Consultation
Speak With an Advisor
Get Started
Explore Services
View Nationwide Services
See Who We Help
Contact Hanover
```

Confirm:

```txt
CTA labels match approved copy.
CTA destinations are correct.
Hero CTAs work.
Mid-page CTAs work.
Final CTAs work.
Footer CTAs work.
No fake guarantee CTA appears.
No maximum refund CTA appears.
```

---

# 27. Forms Checklist

Before launch, confirm:

```txt
Form provider is approved.
Destination email is approved.
CRM destination is approved.
Required fields are approved.
Spam protection is configured.
Privacy language is included.
Thank-you behavior is approved.
Conversion tracking is approved.
Forms work on desktop.
Forms work on mobile.
Form errors are clear.
Form success state is clear.
```

If form integration is not ready, confirm whether placeholder forms are acceptable for preview only.

Do not launch production with broken forms.

---

# 28. Client Portal Checklist

Confirm:

```txt
/client-portal page exists.
Final external portal URL is approved.
Portal link works.
Portal link opens as intended.
No unapproved portal features are described.
Support instructions are approved.
```

If portal URL is missing, add:

```txt
TODO: Confirm final external client portal URL.
```

Do not launch with a fake or placeholder portal link.

---

# 29. Robots.txt Checklist

Confirm:

```txt
robots.txt exists.
robots.txt is available at /robots.txt.
robots.txt allows indexable pages.
robots.txt points to the final sitemap URL.
robots.txt does not block important sections.
```

Recommended:

```txt
User-agent: *
Allow: /

Sitemap: https://www.hanoveraa.com/sitemap.xml
```

---

# 30. Sitemap Checklist

Confirm:

```txt
sitemap.xml exists.
sitemap.xml is available at /sitemap.xml.
Sitemap uses final canonical domain.
Sitemap includes all indexable pages.
Sitemap excludes noindex pages.
Sitemap excludes 404 page.
Sitemap excludes test pages.
Sitemap excludes draft pages.
Sitemap has valid XML.
```

Submit after launch to:

```txt
Google Search Console
Bing Webmaster Tools
```

---

# 31. Redirect Checklist

Confirm `_redirects` exists.

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

Confirm:

```txt
Old URLs redirect to closest new pages.
No redirect loops exist.
No old URLs redirect unnecessarily to homepage.
Redirects use 301 where permanent.
_redirects file is copied into out.
```

---

# 32. Accessibility Checklist

Confirm:

```txt
Pages use semantic HTML.
Each page has one H1.
Heading order is logical.
Buttons are keyboard accessible.
Links are keyboard accessible.
Mobile navigation is keyboard accessible.
Images have approved alt text.
Decorative images use empty alt text.
Form fields have labels.
Color contrast is acceptable.
Focus states are visible.
No major layout traps exist.
```

---

# 33. Mobile Checklist

Test major pages on mobile.

Confirm:

```txt
Header works.
Mobile menu works.
Hero sections scale correctly.
Text is readable.
Buttons are easy to tap.
Cards stack correctly.
Forms work.
Footer is readable.
No horizontal scrolling.
Images scale correctly.
Tables, if any, are responsive.
```

---

# 34. Performance Checklist

Confirm:

```txt
Images are optimized.
Hero images are not oversized.
WebP is used where appropriate.
Fonts load efficiently.
No unnecessary third-party scripts are added.
No layout shifts are obvious.
Core pages load quickly.
Service pages load quickly.
Mobile performance is acceptable.
```

Use:

```txt
Lighthouse
PageSpeed Insights
Cloudflare Analytics
Chrome DevTools
```

---

# 35. Image Checklist

Confirm:

```txt
Images are in public/images.
Image paths work.
Image filenames are lowercase and hyphenated.
Images are compressed.
Images are relevant to the page.
No fake logos appear.
No fake awards appear.
No fake badges appear.
No unreadable text is embedded in images.
Alt text is approved.
```

---

# 36. Legal Page Checklist

Confirm:

```txt
/privacy-policy exists.
/terms-of-use exists.
Legal copy is approved by client.
Privacy language matches form behavior.
No placeholder legal copy remains.
Footer links to legal pages.
```

Do not launch with unapproved legal copy.

---

# 37. Tracking Checklist

Before launch, confirm:

```txt
Google Tag Manager ID is approved.
GA4 ID is approved.
Bing verification is approved.
Google Search Console verification is approved.
Microsoft Clarity is approved, if used.
Tracking scripts are installed correctly.
Tracking does not break static export.
CTA events are planned.
Form submit events are planned.
Click-to-call events are planned.
Client portal click events are planned.
```

Do not add tracking IDs unless approved.

---

# 38. Google Search Console Checklist

After production launch:

```txt
Add or verify https://www.hanoveraa.com.
Submit sitemap.xml.
Inspect homepage.
Inspect top service pages.
Inspect service-area pages.
Inspect tax preparation page.
Inspect online bookkeeping page.
Check indexing status.
Check canonical selection.
Check page indexing errors.
```

---

# 39. Bing Webmaster Checklist

After production launch:

```txt
Add https://www.hanoveraa.com.
Submit sitemap.xml.
Review crawl status.
Review SEO reports.
Review indexing status.
Check for crawl errors.
```

---

# 40. Google Business Profile Checklist

For verified physical offices only, confirm:

```txt
Business name matches.
Address matches.
Phone number matches.
Website URL matches.
Primary category is appropriate.
Service categories are appropriate.
Appointment URL is approved.
Service-area language is accurate.
```

Do not connect unverified service-area pages to fake GBP locations.

---

# 41. Apple Business Connect Checklist

For verified physical offices only, confirm:

```txt
Business name matches.
Address matches.
Phone number matches.
Website URL matches.
Business category is appropriate.
Office location is verified.
Service-area claims are accurate.
```

Do not create Apple location signals for unverified offices.

---

# 42. Final Production QA

Before launch, test:

```txt
https://www.hanoveraa.com
https://hanoveraa.com
http://www.hanoveraa.com
http://hanoveraa.com
```

Expected result:

```txt
All versions resolve or redirect correctly to the canonical HTTPS domain.
```

Confirm:

```txt
No SSL errors.
No mixed content errors.
No redirect loops.
No broken homepage.
No broken navigation.
No broken forms.
No broken sitemap.
No broken robots.txt.
No wrong canonical domain.
```

---

# 43. Final Approval Checklist

Before launch, confirm client approval for:

```txt
Homepage
About page
Contact page
Service pages
Audience pages
Service-area pages
Richmond and Alexandria language
Client portal page
Forms
Phone number
Email address
Office address
Privacy policy
Terms of use
Tracking IDs
Google Business Profile links
Apple Business Connect links
```

---

# 44. Launch Checklist

When everything is approved:

```txt
Merge approved branch into main.
Confirm Cloudflare Pages production deploy passes.
Connect or confirm custom domain.
Confirm HTTPS.
Confirm redirects.
Confirm sitemap.
Confirm robots.txt.
Confirm forms.
Confirm analytics.
Submit sitemap to Google Search Console.
Submit sitemap to Bing Webmaster Tools.
Inspect key URLs.
Monitor first crawl.
```

---

# 45. Post-Launch Checklist

After launch:

```txt
Check homepage.
Check top service pages.
Check contact page.
Check schedule consultation page.
Check client portal page.
Check top local service-area pages.
Check top local + service pages.
Check sitemap.xml.
Check robots.txt.
Check redirects.
Check form submissions.
Check analytics events.
Check Search Console.
Check Bing Webmaster Tools.
Check Cloudflare Analytics.
Check 404s.
Check indexing.
Check speed.
```

---

# 46. Rollback Checklist

If a serious production issue appears:

```txt
Pause further changes.
Identify the issue.
Check latest deployment.
Rollback to previous successful Cloudflare Pages deployment if needed.
Fix issue in Git branch.
Run typecheck.
Run build.
Deploy preview.
QA preview.
Merge to main after approval.
```

Rollback triggers:

```txt
Broken homepage
Broken CSS
Broken navigation
Broken forms
Incorrect DNS
Redirect loop
Wrong domain
Major content error
Security issue
```

---

# 47. Final Prelaunch Rule

Do not launch until:

```txt
The build passes.
The content is approved.
The metadata is approved.
The schema is valid.
The forms work.
The redirects work.
The sitemap works.
The robots.txt file is correct.
The Richmond and Alexandria issue is resolved or safely handled.
No fake claims are present.
No fake local office language is present.
No approved content was changed by Claude Code.
The site exports to /out.
Cloudflare Pages preview is approved.
```

The Hanover website should launch only when it is technically stable, content-accurate, search-ready, conversion-ready, and aligned with the approved Claude Project strategy.
