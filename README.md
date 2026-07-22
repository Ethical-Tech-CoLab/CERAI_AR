# CERAI — Civilian Evacuation Risk Anticipation Index

**[Live site](https://ethical-tech-colab.github.io/CERAI_AR/)** ·
**[Research report](CERAI-Paper.md)** (plain-language, non-technical)

CERAI is a research prototype for anticipating civilian risk during evacuation
operations in armed conflict. It combines multi-category risk indicators
(hazards, infrastructure, population vulnerability, information environment,
weather, and more) into a composite index with Monte Carlo sensitivity
analysis, intended to support International Humanitarian Law (IHL) compliance
review and humanitarian planning.

**Live demo:** https://ethical-tech-colab.github.io/CERAI_AR/

> ⚠️ Research prototype. Outputs are indicative and not a substitute for
> operational decision-making or legal advice.

## What it does

- Interactive scoring across weighted risk categories
- Composite risk gauge with confidence bar
- Monte Carlo sensitivity analysis over uncertain inputs
- Location geocoding, weather integration, and ACLED conflict-event lookup
- Source credibility and data-freshness tagging for each indicator

## Running locally

The app is a single-file HTML prototype. Either:

- Open `index.html` directly in a browser, or
- Serve the directory: `python3 -m http.server 8000` then visit
  `http://localhost:8000/`.

## GitHub Pages

`index.html` at the repo root is served by GitHub Pages from `main` / root,
published at https://ethical-tech-colab.github.io/CERAI_AR/. Pushing to `main`
redeploys it.

## Context

Developed as part of PhD research at NYU School of Law on IHL and AI,
with the aim of making evacuation-risk reasoning more transparent and
auditable for humanitarian and legal audiences (UN, ICRC).

## License

All rights reserved unless otherwise noted. Contact the author before reuse.

---

## Peer Review

The full independent academic peer review of this report is in [PEER-REVIEW.md](PEER-REVIEW.md) (also available as [Word](peer-review/cerai-Peer-Review.docx) under [`peer-review/`](peer-review/)).

**Recommendation:** Major revisions

**What the review found:**

- Article 49 GC IV is mischaracterised as a danger-triggered requirement to evacuate, inverting the IHL default (protection in place; displacement restricted) (S1.3/S5.2/S8.1).
- The tool is described but never evaluated: no weights, no historical-case validation table, no worked example, so the reproducibility claim is uncheckable (S9.3/S10.4).
- The 75% threshold imposes false numeric precision on a qualitative legal standard with no derivation (S5.2/S5.4).

**Noted strength:** The endangerment/feasibility separation (S1.3, S8.3) is a genuinely valuable, ethically sound contribution that stops operational difficulty from silently overriding the duty to protect.
