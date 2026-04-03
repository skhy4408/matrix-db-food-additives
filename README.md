# Food Additive Regulation Database

A comprehensive cross-country comparison database for food additive regulations.

**Live Site:** https://food.matrix-db.com (deployment pending)

## Overview

This database compares food additive regulations across 5 regions:
- 🇪🇺 European Union
- 🇺🇸 United States
- 🇯🇵 Japan
- 🇦🇺 Australia / New Zealand
- 🇨🇦 Canada

## Current Status

- **38 pages** live
- **33 food additives** with complete data
- Full-text search via Pagefind
- SEO optimized (JSON-LD, sitemap, meta tags)
- YMYL-compliant disclaimers

## Tech Stack

- **SSG:** Astro (static)
- **CSS:** Tailwind CSS v4 (CSS-based config)
- **Search:** Pagefind (client-side)
- **Hosting:** Cloudflare Pages
- **Data:** JSON files in `src/data/additives/`

## Project Structure

```
src/
├── data/
│   └── additives/          # 33 additive JSON files
├── layouts/
│   └── BaseLayout.astro
├── pages/
│   ├── index.astro         # Homepage
│   ├── additive/[slug].astro
│   ├── search.astro
│   ├── about.astro
│   ├── privacy-policy.astro
│   └── terms.astro
├── components/
│   ├── Header.astro
│   ├── Footer.astro
│   ├── Disclaimer.astro
│   ├── RegulationStatusBadge.astro
│   ├── FAQSchema.astro     # FAQPage JSON-LD
│   └── BreadcrumbSchema.astro
└── styles/
    └── global.css          # Tailwind v4 config
```

## Development

```bash
# Install dependencies
npm install

# Dev server
npm run dev

# Build (includes Pagefind indexing)
npm run build

# Preview build
npm run preview
```

## Deployment (Cloudflare Pages)

1. Connect GitHub repo to Cloudflare Pages
2. Set build command: `npm run build`
3. Set build output directory: `dist`
4. Set environment variable: `NODE_VERSION=22`
5. Add custom domain: `food.matrix-db.com`

## Data Structure

Each additive has a JSON file with:
- Names & identifiers (E number, INS, CAS, common name, aliases)
- Classification (functional class, source type)
- Regulation status for 5 regions
- Safety evaluations (JECFA ADI, EFSA ADI)
- Natural occurrence & manufacturing
- FAQ auto-generation data

## SEO Features

- ✅ FAQPage JSON-LD on all additive pages
- ✅ BreadcrumbList JSON-LD
- ✅ Auto-generated sitemap (via @astrojs/sitemap)
- ✅ robots.txt
- ✅ OGP meta tags
- ✅ Full-text search (Pagefind)

## YMYL Compliance

This site handles YMYL (Your Money or Your Life) content responsibly:
- ✅ No health/safety advice provided
- ✅ Only factual regulatory information
- ✅ Clear disclaimers on all pages
- ✅ References to official sources
- ✅ Terms of Use with liability disclaimers

## Future Expansion

- Add more additives (target: 350+)
- Country comparison pages
- Food category pages
- Regulatory timeline pages for controversial additives

## License & Credits

**Operated by:** SHOYA KIHARA  
**Email:** contact@matrix-db.com  
**Data Sources:** EU, FDA, JECFA, MHLW, FSANZ, Health Canada

All regulatory data is public information from official government sources.

---

Part of the [Matrix DB](https://matrix-db.com) project.
