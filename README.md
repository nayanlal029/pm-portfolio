# pm-portfolio — product research by Nayan Lal

Self-initiated product strategy studies, written outside-in from public sources and framed as discussion drafts. Each study is a working artifact: interactive visuals plus the companion documents a product team would actually read.

**Primary artifact — Advice Moments**
An outside-in product strategy for growing advice adoption among self-directed investors: a governed personalization layer that surfaces the right advice step at the right moment, built as a phased, eval-governed AI system rather than a black box.

> **Note on discretion:** the published page deliberately does not name the firm it studies. Thresholds and figures are public or illustrative. Keep this README consistent with that: no client name in the repo, so a stray link or a repo screenshot never becomes an issue.

## Live

| What | URL |
| --- | --- |
| Advice Moments (share this one) | `/product_ideas/Advice_Moments_v2/` |
| Case study, long form | `/research/vanguard/` |
| Case study, previous version | `/research/vanguard/v1/` |

Currently served by GitHub Pages from `main` / root. Planned move to Vercel on a `nayanlal.com` subdomain, see **Hosting** below.

## Structure

```
pm-portfolio/
├── index.html                          # redirect to the primary artifact
├── assets/site.css                     # shared design system (tokens, type, components, responsive rules)
├── robots.txt                          # keeps the site out of search engines
├── product_ideas/
│   └── Advice_Moments_v2/              # PRIMARY: self-contained interactive study
│       ├── index.html                  # hero, continuum, simulator, funnel, governance, retention
│       ├── brief_src.html              # source for the gated brief PDF (company name masked)
│       ├── Advice_Moments_Brief.pdf    # gated: opens after the request form
│       └── Nayan_Lal_CV.pdf            # gated: opens after the request form
└── research/
    ├── vanguard/                       # long-form case study + companion PDFs
    │   ├── index.html
    │   ├── brief.html / prd.html       # sources for the PDFs
    │   └── v1/                         # frozen earlier version, self-contained CSS
    └── mergerware/                     # earlier study, intentionally unlinked from the site
```

## Design system

`assets/site.css` holds the tokens and components; each page adds only what is local to it.

- Editorial serif headings, system sans body, deep-emerald accent, warm paper background.
- Fully responsive: verified with zero horizontal overflow at 320px, 375px, and desktop.
- Padding is set with `padding-top` / `padding-bottom` (never the four-value shorthand) on elements that also carry horizontal padding, so section spacing can never null out the side gutters.
- Touch targets enlarge under `@media(pointer:coarse)`.
- Scroll-reveal animation is CSS-gated behind a `.js` class on `<html>`, so content is always visible if JavaScript fails.

## Hosting

**Current:** GitHub Pages, which requires the repo to stay public on a free plan.

**Recommended:** keep the repo **private** and deploy from Vercel.

1. GitHub → Settings → change repository visibility to **Private**.
2. Vercel → Add New Project → import `pm-portfolio` (Vercel reads private repos on the free tier). Framework preset: **Other**. No build command, output directory `.`.
3. Add a domain, e.g. `work.nayanlal.com`, and point a CNAME at Vercel from the `nayanlal.com` DNS.
4. Optional but recommended: add `vercel.json` rewrites so the share link is clean, e.g. `/advice-moments` → `/product_ideas/Advice_Moments_v2/`.

Notes on the alternatives: GitHub Pages from a private repo needs GitHub Pro, and the site is public regardless. Netlify and Cloudflare Pages also deploy private repos free. If the page itself ever needs to be login-gated, Cloudflare Access is the cheapest path.

## Regenerating the PDFs

Rendered from the source HTML with headless Chrome:

```bash
CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
cd product_ideas/Advice_Moments_v2
"$CHROME" --headless=new --no-pdf-header-footer --virtual-time-budget=4000 \
  --print-to-pdf="Advice_Moments_Brief.pdf" "file://$PWD/brief_src.html"
```

## Conventions

- No em dashes in any published copy.
- Never name the firm on the public page or in this repo.
- All figures are public or explicitly illustrative and directional, meant to start a conversation, not to represent any firm's actual data, roadmap, or economics.
- Independent work, not affiliated with or endorsed by any company discussed, and not based on any confidential information.

Prepared by Nayan Lal · nayanlal1909@gmail.com · linkedin.com/in/nayan-lal
