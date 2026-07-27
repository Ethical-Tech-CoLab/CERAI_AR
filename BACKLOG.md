# Backlog

Known gaps, in the order they would mislead a reader.

---

## Credibility review — 2026-07-27

A hostile-but-fair peer-review sweep of the report copy (canonical in
[CERAI-Paper.md](CERAI-Paper.md), mirrored on the site in
`website/src/content/publications/cerai.ts`). Fix in both places. See also
[PEER-REVIEW.md](PEER-REVIEW.md).

### 1. The report misreads the IHL its threshold depends on

Three checkable international-law errors an IHL reader would catch, all touching
the 75% "Article 49 obligation" threshold that the model is built around:

- **Article 49 is a prohibition, not a mandate.** GC IV Art 49 *prohibits*
  forcible transfer and only *permits* evacuation as a narrow exception in
  *occupied territory* — it does not require it, and it does not apply to armed
  conflict generally. Reword to "Art 49 permits evacuation of an occupied area
  as an exception to its prohibition on forcible transfer," and stop describing
  75% as an "obligation."
- **Art 16 / 24 descriptors are wrong.** §08 labels GC IV "Articles 16 and 24"
  as protecting "children and the elderly," but Art 16 covers the wounded,
  sick, infirm, and expectant mothers, and no GC IV article specifically
  protects "the elderly" — the exact confusion the Evacuation Simulator report
  corrects for its sister project. Cite Art 24 (children) and Art 16
  (wounded/sick/infirm/expectant mothers) accurately; ground any "elderly"
  claim in Customary Rule 138.
- **AP I Art 78 is misapplied.** It is cited for internal child evacuation, but
  Art 78 governs only evacuation of children to a *foreign country* under
  strict consent conditions. Rely on AP I Art 77 and GC IV Arts 24/50 for
  internal child protection.

**Why it matters.** The legal citations are the report's authority; getting them
wrong hands a specialist reader an easy discredit.

### 2. The validation dataset is uncited

§01/§05/§10 describe "a database of documented real-world evacuation operations
since the year 2000" of "a few dozen documented cases" used to check outputs for
face validity, with no source in the works cited. Cite the underlying case
sources, or explicitly label the database as the researcher's own unpublished
compilation.

---

## Peer-review findings (from PEER-REVIEW.md, 22 Jul 2026 — "major revisions")

Full referee report in [PEER-REVIEW.md](PEER-REVIEW.md). Verify each against the
current report copy and check off any already fixed.

Major:
- [ ] **Article 49 mischaracterised (§1.3, §5.2, §8.1).** "Requires evacuation"
      inverts the law: Art 49 is occupation-specific, permissive-exceptional,
      and paired with a duty of return the tool never models. Re-anchor the
      endangerment rationale in the precautions rules (AP I Arts 57–58,
      customary Rules 15–24) and protection-from-attack (AP I Art 51); recast
      Art 49 as a *constraint* on evacuation. (Same as credibility item 1 above;
      this is the single highest-value fix.)
- [ ] **The tool is described but never evaluated (§5.5, §9.3–9.4, §10.4).** No
      weight vector, no validation table, no worked example anywhere. Publish
      the weights, aggregation formulas, and a face-validity table scoring the
      named cases (Aleppo, Mariupol, Mosul, Kabul) against independent
      characterisations, plus one end-to-end scenario.
- [ ] **The 75% threshold is false precision with no derivation (§5.2, §5.4).**
      A single cutpoint on a qualitative treaty phrase, with worst-case defaults
      pushing under-informed scores toward it. Derive it empirically or replace
      with a banded "consult legal review" zone; disclose the default
      interaction; suppress time-to-threshold when confidence is low.
- [ ] **Dual-use / misuse risk treated as a one-line caveat (§10.6, §12.1).** A
      high score tied to a treaty article can be invoked to *legitimise*
      unlawful displacement. Add a misuse section: outputs cannot supply legal
      justification; foreground coercion/consent and non-refoulement; name any
      guardrails.

Minor: no references section (m1); literature positioning limited to INFORM
(m2); aggregation math prose-only and "no double-counting" unproven (m3); Monte
Carlo varies inputs not weights (m4); authorship unclear (m5); external data
licensing/terms unaddressed (m6); non-refoulement listed flat among IHL
provisions (m7); case-count vague/inconsistent (m8).
