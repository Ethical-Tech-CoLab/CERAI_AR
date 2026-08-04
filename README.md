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

**Finding status** (updated 2026-08-04):

| Finding | Status |
|---------|--------|
| Article 49 GC IV mischaracterised as danger-triggered duty (§1.3/§5.2/§8.1) | ✅ Fixed |
| Art 16/24 descriptors wrong; Art 78 misapplied to internal displacement (§8.1) | ✅ Fixed |
| Tool described but never evaluated: no weights, no validation table (§9.3/§10.4) | ✅ Fixed |
| No references section | ✅ Fixed |
| Authorship unclear ("advised by" vs. "developed by") | ✅ Fixed |
| Non-refoulement listed flat among IHL provisions (different legal regime) | ✅ Fixed |
| Monte Carlo varies inputs, not weights — limitation unstated | ✅ Fixed |
| Case-count vague/inconsistent ("few dozen" vs. actual N) | ✅ Fixed |
| Dual-use/misuse risk treated as one-line caveat | ✅ Fixed |
| 75% threshold: false precision, no derivation | ⚠️ Partially addressed |
| Literature positioning limited to INFORM Severity | 🔲 Open |
| External data licensing/terms unaddressed | 🔲 Open |

**Noted strength:** The endangerment/feasibility separation (§1.3, §8.3) is a genuinely valuable, ethically sound contribution that stops operational difficulty from silently overriding the duty to protect.

### Revisions applied (2026-08-04)

**Legal citations corrected** across `index.html`, `CERAI.html`, and `CERAI-Paper.md`:

- **Art 49:** 75% marker re-anchored in AP I Arts. 51, 57, 58 (IAC) and Common Art. 3 / AP II Art. 17 (NIAC). Art. 49 stated as prohibition on forcible transfer from occupied territory; evacuation a narrow conditional permission carrying a duty of return.
- **Art 16/24/78:** GCIV Art. 16 correctly identified as covering the wounded, sick, infirm, and expectant mothers. Children cited under GCIV Arts. 24 and 50 and AP I Art. 77. Older persons grounded in Customary IHL Rule 138. AP I Art. 78 limited to its actual scope: foreign-country evacuation only.
- **Non-refoulement:** Flagged as refugee law / IHRL (1951 Refugee Convention Art. 33), distinct from IHL, engaged where evacuees cross international borders.

**Tool evaluated.** `CERAI-Paper.md` §9.3 now publishes the full weight vector, aggregation formulas, and a face-validity table scoring four anchor cases (Mariupol 2022, East Aleppo 2016, Kabul 2021, Op Raahat Yemen 2015). Discrepancy ≤ ±2 points against retrospective ground-truth assessments.

**Misuse section added** (`CERAI-Paper.md` §10.8): outputs cannot supply legal justification; coercion/consent problem named; non-refoulement and return obligation specified; required output language at threshold stated.

**References added:** 20-citation references section covering primary legal instruments, customary IHL, methodology, and historical case sources.

**Other:** Authorship corrected ("Developed by Teresa Cantero"); case count stated as 21 with source attribution; Monte Carlo weight-sensitivity limitation stated explicitly (§10.9).
