# Hanover Accountants & Advisors — Website Rebuild

A full website rebuild for **Hanover Accountants & Advisors**, positioning the firm as a
nationwide online accounting, tax, bookkeeping, payroll, and advisory practice with strong
local service-area visibility for Georgia and Virginia markets.

## Status

🚧 **Pre-build.** Repository is initialized and connected to GitHub. The Next.js application
has not been scaffolded yet. See [`docs/00-project-control/project-brief.md`](docs/00-project-control/project-brief.md)
for the complete project specification.

## Planned Tech Stack

- Next.js + TypeScript + React
- Static export (`output: "export"`, output dir `out/`)
- Cloudflare Pages (deployment target)
- GitHub (source control)

## Local Development (once scaffolded)

```bash
npm install      # install dependencies
npm run dev      # run local dev server
npm run build    # build static export to /out
```

## Documentation

Project planning, research, strategy, and build docs live under [`docs/`](docs/),
organized into numbered subfolders. The full set is complete:

- `00-project-control/` — project-brief, project-overview, do-not-invent
- `01-research/` — source-site-analysis, full-build-list
- `02-strategy/` — url-slug-strategy, site-architecture
- `03-seo-aeo-geo/` — schema-plan, metadata-plan
- `04-brand-content/` — content-style-guide
- `05-matrices/` — services-data-plan, audience-service-matrix, location-service-matrix
- `06-technical/` — folder-structure, nextjs-static-export, cloudflare-pages-deployment
- `07-claude-project/` — claude-project-instructions, claude-code-handoff-prompt
- `08-qa-launch/` — prelaunch-checklist

Start with the [project brief](docs/00-project-control/project-brief.md).
