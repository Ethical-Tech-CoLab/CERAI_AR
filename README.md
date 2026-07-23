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

- Article 49 GC IV is mischaracterised as a danger-triggered requirement to evacuate, inverting the IHL default (protection in place; displacement restricted) (S1.3/S5.2/S8.1). — **Fixed.**
- The tool is described but never evaluated: no weights, no historical-case validation table, no worked example, so the reproducibility claim is uncheckable (S9.3/S10.4). — *Open.*
- The 75% threshold imposes false numeric precision on a qualitative legal standard with no derivation (S5.2/S5.4). — *Open.*

**Noted strength:** The endangerment/feasibility separation (S1.3, S8.3) is a genuinely valuable, ethically sound contribution that stops operational difficulty from silently overriding the duty to protect.

### Revisions applied

**Legal anchor corrected.** The 75% endangerment marker is no longer tied to Article 49 GC IV. It is now anchored to the provisions that actually create an affirmative duty to protect civilians from the effects of hostilities: AP I Articles 51, 57, and 58 in international armed conflict, and Common Article 3 with AP II Article 17 in non-international armed conflict — the regime governing most of the historical case dataset.

Article 49 is now stated in its true role: primarily a **prohibition** on individual or mass forcible transfer and deportation from occupied territory, within which evacuation is a narrow conditional permission for an Occupying Power (temporary, adequate accommodation, return once hostilities in the area cease). The IHL default is protection in place, with displacement restricted rather than required, so Article 49 constrains and conditions an evacuation rather than triggering one. CERAI now uses it that way — bearing on whether a proposed movement would itself be lawful and protective (the Protection at Destination input), not on whether danger demands action. The IAC/NIAC crossover is stated explicitly rather than resolved by stretching Article 49 beyond its scope.

Applied in `index.html` (gauge marker tooltip, methodology section, and the runtime IHL-obligation strings), mirrored in the unreferenced `CERAI.html` copy, and in `CERAI-Paper.md` (S5.2 and the S8 provision list).
