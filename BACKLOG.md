# Backlog

Known gaps, in the order they would mislead a reader.

---

## Credibility review — 2026-07-27

A hostile-but-fair peer-review sweep of the report copy (canonical in
[CERAI-Paper.md](CERAI-Paper.md), mirrored on the site in
`website/src/content/publications/cerai.ts`). Fix in both places. See also
[PEER-REVIEW.md](PEER-REVIEW.md).

### 1. The report misreads the IHL its threshold depends on — **Fixed**

Three checkable international-law errors an IHL reader would catch, all touching
the 75% "Article 49 obligation" threshold that the model is built around:

- **Article 49 is a prohibition, not a mandate.** — **Fixed.** The 75%
  threshold is now anchored in AP I Arts. 51, 57, and 58 (IAC) and Common
  Art. 3 / AP II Art. 17 (NIAC). Article 49 is stated in its correct role as a
  prohibition on forcible transfer from occupied territory, with evacuation as a
  narrow conditional permission carrying a duty of return. Applied in
  `index.html`, `CERAI.html`, and `CERAI-Paper.md` §5.2, §8.1.

- **Art 16 / 24 descriptors are wrong.** — **Fixed.** GC IV Art. 16 now
  correctly identified as covering the wounded, sick, infirm, and expectant
  mothers (not "children and the elderly"). GC IV Arts. 24 and 50 cited for
  children. Older persons now grounded in Customary IHL Rule 138. AP I Art. 77
  cited for children in IAC. Applied in `index.html` and `CERAI.html` tooltips
  and weight tables, and in `CERAI-Paper.md` §8.1.

- **AP I Art 78 is misapplied.** — **Fixed.** Art. 78 is now stated in all
  three files as governing only evacuation of children to a *foreign country*
  under strict consent conditions, not internal displacement. Internal child
  protection relies on AP I Art. 77, GCIV Arts. 24 and 50.

### 2. The validation dataset is uncited — **Fixed**

§01/§05/§10 previously described "a database of documented real-world evacuation
operations since the year 2000" with no source. Now fixed in `CERAI-Paper.md`:

- §9.3 now states the dataset is the researcher's own compilation from UN
  reports, ICRC operational reviews, IOM displacement tracking, and published
  academic analyses. Case count given as 21.
- §10.4 updated from "a few dozen documented cases" to "21 documented cases"
  with source attribution.
- A references section with 20 numbered citations has been added at the end of
  `CERAI-Paper.md`.

---

## Peer-review findings (from PEER-REVIEW.md, 22 Jul 2026 — "major revisions")

Full referee report in [PEER-REVIEW.md](PEER-REVIEW.md). Status updated
2026-08-04.

Major:
- [x] **Article 49 mischaracterised (§1.3, §5.2, §8.1).** — **Fixed.** See
      Credibility item 1 above.
- [x] **The tool is described but never evaluated (§5.5, §9.3–9.4, §10.4).**
      — **Fixed.** §9.3 in `CERAI-Paper.md` now publishes the full weight
      vector, aggregation formula, and a face-validity table scoring Mariupol
      2022, East Aleppo 2016, Kabul 2021, and Op Raahat Yemen 2015 against
      ground-truth retrospective assessments. Discrepancy ≤ ±2 points across
      all four anchor cases.
- [ ] **The 75% threshold is false precision with no derivation (§5.2,
      §5.4).** — *Partially addressed.* §9.3a now states the threshold was
      derived through face-validity assessment against the historical case
      dataset. Full empirical derivation and confidence-band treatment remain
      a planned next step; the threshold tooltip in the tool notes this.
- [x] **Dual-use / misuse risk treated as a one-line caveat (§10.6,
      §12.1).** — **Fixed.** New §10.8 in `CERAI-Paper.md` adds a dedicated
      misuse section covering: (a) outputs cannot supply legal justification,
      (b) coercion/consent problem, (c) non-refoulement and the return
      obligation, (d) required output language at threshold.

Minor:
- [x] **m1 — No references.** — **Fixed.** 20-citation references section
      added to `CERAI-Paper.md`.
- [ ] **m2 — Literature positioning limited to INFORM.** — *Open.* Planned
      for a future revision; would require engagement with IASC/OCHA and ICRC
      protection literature.
- [x] **m3 — Aggregation math prose-only; "no double-counting" unproven.**
      — **Fixed.** Weight vector published in `CERAI-Paper.md` §9.3.
      Aggregation formulas (weighted sum for D1, geometric mean for D2,
      multiplicative for D3) already documented in the tool's Methodology
      panel and cross-referenced in §9.1–9.2.
- [x] **m4 — Monte Carlo varies inputs not weights.** — **Fixed.** New
      §10.9 in `CERAI-Paper.md` acknowledges this limitation explicitly and
      flags weight-sensitivity analysis as a planned enhancement.
- [x] **m5 — Authorship unclear.** — **Fixed.** Attribution in
      `CERAI-Paper.md` now states "Developed by Teresa Cantero" (not
      "Development advised by").
- [ ] **m6 — External data licensing/terms unaddressed.** — *Open.* Planned
      for a future revision. ACLED, GDELT, Nominatim/OSM, and Open-Meteo
      terms noted in the tool's Methodology panel; a formal compliance
      statement is pending.
- [x] **m7 — Non-refoulement listed flat among IHL provisions.** — **Fixed.**
      Non-refoulement now explicitly identified in `CERAI-Paper.md` §8.1 and
      in `index.html` / `CERAI.html` weight table as a rule of refugee and
      international human rights law (1951 Refugee Convention Art. 33),
      distinct from IHL, engaged where evacuees cross international borders.
- [x] **m8 — Case-count vague/inconsistent.** — **Fixed.** §10.4 now states
      "21 documented cases" with source attribution. The anchor-case table in
      §9.3a gives the specific cases used for face-validity checks.
