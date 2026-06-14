# Nayan Lal — Product research portfolio (`pm-portfolio`)

Self-initiated product strategy and research studies by Nayan Lal, AI Product Manager. Each study is built from public sources and framed as a discussion draft.

**▶ Live:** https://nayanlal029.github.io/pm-portfolio/ *(resolves once GitHub Pages is enabled — see below)*

## Structure

```
pm-portfolio/
├── index.html                 # landing page
├── assets/site.css            # shared design system (tokens, type, components)
├── robots.txt                 # keeps the site out of search engines
└── research/
    ├── vanguard/              # Advice Moments — Vanguard Personal Investor advice growth
    │   ├── index.html         # interactive case study (centerpiece)
    │   ├── brief.html         # executive PR-FAQ (source for the PDF)
    │   ├── prd.html           # full AI-PRD (source for the PDF)
    │   ├── Nayan_Lal_Vanguard_Advice_Moments_Brief.pdf
    │   └── Nayan_Lal_Vanguard_Advice_Moments_PRD.pdf
    └── mergerware/            # MergerWare — M&A SaaS product research
        ├── index.html         # interactive competitive landscape
        └── MergerWare_Product_Strategy_and_PRD.pdf
```

## Projects

### Advice Moments — Vanguard Personal Investor advice growth (June 2026)
An outside-in product strategy for growing advice adoption among self-directed investors: a governed personalization layer that surfaces the right advice step at the right moment, built as a phased, eval-governed AI system. Three layers: an interactive case study, an executive PR-FAQ brief, and a full AI-PRD written as a behavioral contract (eval thresholds, failure modes, governance).

### MergerWare — M&A SaaS product research (June 2026)
An interactive map of the M&A software market plus a strategy brief and flagship PRD for the leading bet (the "Value Engine"). Carried over from the earlier `pm-research-portfolio` repo.

## Regenerating the Vanguard PDFs

The PDFs are rendered from the source HTML with headless Chrome:

```
CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
cd research/vanguard
"$CHROME" --headless=new --no-pdf-header-footer --virtual-time-budget=4000 \
  --print-to-pdf="Nayan_Lal_Vanguard_Advice_Moments_Brief.pdf" "file://$PWD/brief.html"
"$CHROME" --headless=new --no-pdf-header-footer --virtual-time-budget=4000 \
  --print-to-pdf="Nayan_Lal_Vanguard_Advice_Moments_PRD.pdf" "file://$PWD/prd.html"
```

## Enabling the live site

After pushing, go to **Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / `/ (root)` → Save**. The live URL resolves in about a minute.

## Adding a new study

1. Create `research/<project>/` with an `index.html` that links `../../assets/site.css`.
2. Add a project card to the root `index.html`.
3. Update this README and push.

## Backlog (future studies)

- **Proactive retention / early-warning** — AI early-warning to detect at-risk clients and trigger proactive saves.
- **Personal Investor AI Copilot** — next-best-action personalization across the digital experience (onboarding, cash, mobile).

## Notes

- Intentionally kept out of search engines (`noindex` + `robots.txt`) — share by link. To make it discoverable later, remove the `noindex` meta tags and `robots.txt`.
- All figures are from public sources, directional, and meant to start a conversation, not serve as a benchmark. Studies are independent work, not affiliated with or endorsed by any company discussed, and not based on any confidential information.
- Prepared by Nayan Lal · nayanlal1909@gmail.com · linkedin.com/in/nayan-lal
