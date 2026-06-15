# Advice Moments: product research by Nayan Lal (`pm-portfolio`)

A self-initiated product strategy study, **June 2026**, built entirely from public sources and framed as a discussion draft. The public site is focused on one study: **Advice Moments**, an outside-in product strategy for growing advice adoption among self-directed Vanguard investors.

**▶ Live (once GitHub Pages is enabled):**
- Landing: https://nayanlal029.github.io/pm-portfolio/
- The study (current): https://nayanlal029.github.io/pm-portfolio/research/vanguard/
- The study (previous version): https://nayanlal029.github.io/pm-portfolio/research/vanguard/v1/

## Structure

```
pm-portfolio/
├── index.html                       # landing (Advice Moments cover, nav, mini continuum)
├── assets/site.css                  # shared design system
├── robots.txt                       # keeps the site out of search engines
└── research/
    ├── vanguard/                    # Advice Moments (current version)
    │   ├── index.html               # interactive case study
    │   ├── brief.html / prd.html    # source for the PDFs
    │   ├── Nayan_Lal_Vanguard_Advice_Moments_Brief.pdf
    │   ├── Nayan_Lal_Vanguard_Advice_Moments_PRD.pdf
    │   └── v1/                       # previous version, self-contained (frozen CSS)
    └── mergerware/                   # earlier study, kept in the repo but not linked from the site
```

## The study: Advice Moments

*Advice, the moment an investor crosses into the threshold.* A governed personalization layer that surfaces the right advice step to self-directed investors at the right moment, built as a phased, eval-governed AI system. Interactive pieces: a concentric advice continuum, a "moment" simulator across real public thresholds, a marketing-to-advice funnel (MGL → MQL → advisor call → DA/PA/PAS), a retention/churn view, plus an executive PR-FAQ brief and a full AI-PRD written as a behavioral contract.

## Versions

- **Current:** `research/vanguard/`: wider desktop layout, scroll-spy nav, ring labels, funnel and retention visuals.
- **Previous:** `research/vanguard/v1/`: the earlier version, preserved self-contained with its own frozen stylesheet so it renders exactly as it did.

## MergerWare

An earlier M&A SaaS product study lives at `research/mergerware/`. It is intentionally **not linked** from the public landing so the live site stays focused on a single company; the files remain in the repo as prior work.

## Regenerating the PDFs

Rendered from the source HTML with headless Chrome:

```
CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
cd research/vanguard
"$CHROME" --headless=new --no-pdf-header-footer --virtual-time-budget=4000 \
  --print-to-pdf="Nayan_Lal_Vanguard_Advice_Moments_Brief.pdf" "file://$PWD/brief.html"
"$CHROME" --headless=new --no-pdf-header-footer --virtual-time-budget=4000 \
  --print-to-pdf="Nayan_Lal_Vanguard_Advice_Moments_PRD.pdf" "file://$PWD/prd.html"
```

## Enabling the live site

**Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / `/ (root)` → Save.** All paths above resolve within ~a minute. One toggle publishes every version.

## Notes

- Kept out of search engines (`noindex` + `robots.txt`): share by link. Make the repo private if you prefer (note: GitHub Pages on a private repo needs a paid plan).
- All figures are public or illustrative and directional, meant to start a conversation. Independent work, not affiliated with or endorsed by any company discussed, and not based on any confidential information.
- Prepared by Nayan Lal · nayanlal1909@gmail.com · linkedin.com/in/nayan-lal
