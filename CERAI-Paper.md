# The Civilian Evacuation Risk Anticipation Index (CERAI)

### A Research Report on a Decision-Support Tool for Protecting Civilians During Evacuations in Armed Conflict

*Prepared as a plain-language review of the CERAI research prototype*
*based on the software and documentation contained in this repository*

---

## Foreword

When war forces people to flee their homes, the decisions that follow are
among the most consequential a humanitarian actor or a government can make.
Should a community be moved now, or is it safer to shelter in place? Is a
corridor genuinely open, or open only on paper? Who among the population, such
as children, the elderly, and the sick, will be least able to make the journey?
These questions are usually answered under extreme time pressure, with
incomplete information, and with lives hanging on the outcome.

The Civilian Evacuation Risk Anticipation Index, known as CERAI, is a research
prototype built to make this reasoning more structured, more transparent, and
more open to scrutiny. This report explains, in non-technical language, what
CERAI is, what it does, how it works, and, just as important, what it does
not claim to do. It is intended for a policy, humanitarian, and legal
audience rather than a technical one.

---

## 1. Executive Summary

1.1 CERAI is a research prototype, an experimental software tool, that
helps analysts think through the risks civilians face during an evacuation in
an armed conflict. It does not make decisions. It organises evidence and
expert judgment into a clear, repeatable structure so that human
decision-makers can see how a conclusion was reached.

1.2 The tool asks a set of structured questions across several categories of
risk: the intensity of fighting, the proximity of armed groups, the
condition of escape routes, the vulnerability of the affected population, the
weather, the availability of food and water, and the capacity of the place
people would move to. It then combines these inputs into clear summary scores.

1.3 CERAI's central and most distinctive idea is to keep two questions
separate that other tools tend to blend together:

   - Endangerment: *How dangerous is it for civilians to remain where
     they are?*
   - Feasibility: *Is an organised, safe evacuation actually possible
     right now?*

   Keeping these apart matters for legal reasons. Under International
   Humanitarian Law (IHL), the obligation to protect and consider moving
   civilians arises from the *danger* they face, not from whether an
   evacuation happens to be convenient or operationally easy. A situation that
   is extremely dangerous but where evacuation is currently blocked does not
   remove the obligation to protect civilians; it makes the case for urgent
   political and diplomatic action even stronger.

1.4 The tool is explicitly aligned with well-established humanitarian and legal
frameworks, and it draws comparisons to a database of documented real-world
evacuation operations since the year 2000 (for example, the sieges of Aleppo
and Mariupol, the battle of Mosul, and the evacuation of Kabul).

1.5 CERAI is delivered as a single self-contained web page that runs in an
ordinary browser and is published as a live public demonstration. It is
intended for academic demonstration only and is not authorised for
operational use without expert validation.

1.6 The tool was developed as part of masters research at the New York
University (NYU) Center for Global Affairs, focused on the intersection of International
Humanitarian Law and artificial intelligence, with the stated aim of making
evacuation-risk reasoning more transparent and auditable for humanitarian and
legal audiences such as the United Nations and the International Committee of
the Red Cross (ICRC).

---

## 2. Background and Rationale

2.1 The problem. Evacuation decisions in conflict are high-stakes and
made under pressure. Experienced humanitarian coordinators rely heavily on
accumulated judgment and memory of past operations. This expertise is
invaluable, but it is often implicit, held in the minds of individuals, and
therefore difficult to review, to explain to others, or to reproduce
consistently across different teams and situations.

2.2 The gap. Existing humanitarian severity tools (such as the widely used
INFORM Severity Index) are designed to measure the overall intensity of a
humanitarian crisis. They are not built specifically around the legal and
operational logic of an evacuation decision, and they tend to merge the
question of *how bad the situation is* with the question of *how accessible it
is*. For an evacuation decision, blending these can be misleading and, in a
legal sense, dangerous.

2.3 The response. CERAI proposes a purpose-built framework for the
evacuation question. Its guiding principle is that a good decision-support
tool should be transparent (every number can be traced back to the inputs
and reasoning that produced it), structured (it forces the analyst to
consider the right questions in the right order), and reproducible (the
same inputs always produce the same outputs, so the reasoning can be checked
by others).

2.4 CERAI describes itself as a structured aid rather than a successor to
expert judgment. It preserves what works in expert practice, namely
recognising patterns from past operations, while making that pattern
recognition visible and open to challenge.

---

## 3. Objectives

The tool is designed to:

3.1 Provide a transparent and repeatable method for assessing civilian
risk during a potential evacuation.

3.2 Separate the assessment of danger (endangerment) from the assessment
of operational possibility (feasibility), so that legal obligations are not
obscured by practical constraints.

3.3 Make explicit how population vulnerability, including the presence of
children, elderly people, people at risk of gender-based violence, and those
with limited resources or mobility, changes the real level of risk faced by a
community.

3.4 Anchor each assessment against documented historical cases, surfacing
which past operations most resemble the current situation.

3.5 Communicate the resulting analysis in a form useful to humanitarian
coordinators, political decision-makers, and legal reviewers, including
explicit references to the relevant IHL obligations.

3.6 Be honest about uncertainty by showing how confident the assessment is
and how sensitive the conclusion is to assumptions.

---

## 4. How CERAI Works

The tool is organised around three connected "dimensions." A user works
through them by answering structured questions, and the tool presents the
results on a set of easy-to-read dials and summaries.

### 4.1 Dimension 1: Endangerment ("How dangerous is it to remain?")

The analyst provides information across a range of risk factors, including:

- the intensity of ongoing hostilities;
- how close armed groups are to the civilian population;
- indicators that an attack may be imminent;
- the risk of the conflict escalating;
- the presence of chemical or biological threats;
- non-conflict hazards (such as extreme weather or disease);
- the availability of food, water, and energy; and
- the proportion of the population that is especially vulnerable.

Each factor is weighted according to how central it is to the corresponding
legal obligation. For example, the intensity of hostilities carries the
largest single weight, reflecting the core IHL protection of civilians from
attack. The tool combines these into a single endangerment score,
displayed on a gauge with a clearly marked threshold (see Section 5).

### 4.2 Dimension 2: Feasibility ("Is an organised evacuation possible now?")

This dimension assesses whether an evacuation could actually be carried out
safely, broken into three sub-questions:

- Zone Exit: Can people get out of the danger zone at all? (Is a corridor
  open? Have armed groups consented? Are routes mined? Is an attack imminent?)
- Route Conditions: Is the journey survivable? (Weather, daylight,
  availability of transport, mines along the route, and the distance to
  safety.)
- Protection at Destination: Is the place people are moving to actually
  safe and able to receive them? (Shelter, medical capacity, security,
  willingness to receive, and consent of relevant actors.)

Each sub-question produces its own score, and the three are combined into a
composite feasibility score.

### 4.3 Dimension 3: Vulnerability ("Who is most at risk, and how does that change the picture?")

The same objective situation is not equally dangerous for everyone. A route
that an able-bodied adult can walk may be impassable for young children, the
elderly, or the chronically ill. Dimension 3 captures the make-up of the
affected population and produces an adjustment multiplier that can raise
or lower the risk picture within defined bounds.

Importantly, vulnerability affects *both* of the other dimensions, but for
different reasons: it increases the harm a given hazard causes
(endangerment), and it reduces the navigability of a given route
(feasibility). The tool treats these as two distinct effects rather than
double-counting the same factor.

### 4.4 The Decision-Support Briefing

Beyond the scores, CERAI generates a written briefing aimed at humanitarian
and political decision-makers. It highlights which IHL obligations are
triggered, what the scores mean in practice, and where the greatest
uncertainties or blocking constraints lie.

---

## 5. Reading the Results

5.1 Risk gauges. The endangerment and feasibility scores are shown on
colour-coded dials running from low risk (green) to extreme risk (deep red and
purple), with intermediate bands (moderate, elevated, high, critical).

5.2 The 75% threshold. The endangerment gauge carries a marker at 75%.
This represents the point at which conditions are considered to demand
evacuation under Article 49 of the Fourth Geneva Convention (which requires
evacuation "where the security of the population or imperative military reasons
so demand"). The threshold is indicative only. It flags that conditions
resemble those which have historically triggered legal obligations; it does
not itself create a legal obligation, and human legal judgment is always
required.

5.3 Confidence bar. The tool shows how much of the assessment is based on
real, entered data versus cautious "worst-case" default assumptions. When
information is missing, CERAI deliberately assumes a higher-risk default (in
keeping with the precautionary logic of IHL) and lowers the displayed
confidence accordingly. A higher confidence figure means the conclusion rests
on specific evidence rather than assumptions.

5.4 Trajectory and time-to-threshold. The tool tracks how the danger score
is changing over the course of a session, whether deteriorating, stable, or
improving, and offers a rough projection of how many days it might take to
reach the 75% obligation threshold if current trends continue. This is
described explicitly as a planning aid only, since real situations rarely
change in a straight line.

5.5 Historical comparisons. CERAI compares the current situation against a
database of documented evacuation operations and surfaces the closest
historical analogues. This mirrors how experienced coordinators reason, saying
"this looks like Mariupol" or "this resembles Mosul," but it makes that
comparison explicit and open to challenge.

---

## 6. Testing Assumptions: Sensitivity and "What-If" Analysis

6.1 Monte Carlo sensitivity analysis. Because many inputs are uncertain,
CERAI can run a simulation (a "Monte Carlo" analysis) that repeatedly varies
the uncertain inputs within plausible ranges and observes how often the
conclusion changes. This shows the decision-maker whether the assessment is
robust or whether it hinges on a few uncertain assumptions.

6.2 What-If pressure test. The tool identifies the handful of variables
that most strongly influence the outcome and lets the user adjust them to see
the effect immediately. This supports scenario planning without altering the
main assessment.

---

## 7. Connections to Live Data

To move beyond manual entry, the prototype connects to several external,
publicly available data sources:

- Location look-up (Nominatim / OpenStreetMap): converts a place name into
  coordinates.
- Weather (Open-Meteo): retrieves current weather conditions for the
  assessed location.
- Conflict events (ACLED): retrieves recorded conflict-event data, which
  can drive a data-based trajectory calculation.
- News signals (GDELT): surfaces recent news articles relevant to the
  location.

The documentation also describes planned future connections to established
humanitarian data systems, including UN OCHA / ReliefWeb access monitoring,
the EU Global Conflict Risk Index (GCRI), FEWS NET / IPC food-security data,
and the INFORM Severity Index, as pathways to make the tool more
automatically data-driven over time.

Each manually entered figure can also be tagged with a source credibility
level (from unverified, through media and NGO reporting, to UN/ICRC verified)
and a data-freshness indicator, so that the reliability and age of the
underlying evidence are visible in the assessment itself.

---

## 8. Grounding in International Humanitarian Law

8.1 A defining feature of CERAI is that its structure is tied directly to
specific IHL obligations. The weighting of each risk factor is justified by
reference to the legal provision it relates to. Examples cited in the tool
include:

- Fourth Geneva Convention, Article 49: evacuation where security
  demands;
- Additional Protocol I, Article 51: protection of civilians from
  attack;
- Additional Protocol I, Article 57: precautions in attack, including
  effective advance warning;
- Additional Protocol I, Article 58: passive precautions, keeping
  civilians away from military objectives;
- Fourth Geneva Convention, Article 54 and Additional Protocol I,
  Article 70: prohibition of starvation and provision of relief;
- special protections for children and the elderly (GCIV Arts. 16, 24; AP I
  Arts. 77-78); and
- principles of non-refoulement and the safety of the receiving location.

8.2 The tool references established humanitarian doctrine and coordination
frameworks from bodies including the ICRC, UN OCHA, UNHCR, WHO, IOM, and
UN mine-action services (UNMAS), as well as the Ottawa Treaty on landmines and
the Chemical Weapons Convention.

8.3 The legal design principle is stated plainly: low feasibility must never be
allowed to appear to extinguish the obligation to protect civilians. A
high-danger, low-feasibility situation is precisely the case that should
escalate political engagement rather than be quietly resolved by an algorithm.

---

## 9. Methodological Choices

9.1 Why combine scores using a "geometric mean" rather than a simple
average. CERAI deliberately combines sub-scores in a way that penalises a
single very bad factor heavily. In plain terms: if the escape corridor is
essentially closed, the overall feasibility should be critically low no matter
how good the weather is. A simple average would let good factors "cancel out"
a fatal blocking constraint; CERAI's approach does not allow that.

9.2 Why vulnerability is a multiplier, not just another added factor.
Vulnerability changes how the objective conditions actually affect people, so
it is applied as an adjustment (within bounded limits) to the objective scores
rather than being averaged in alongside them.

9.3 Where the weights come from. The current weights were assigned by the
researcher based on a review of IHL doctrine and checked for "face validity"
against documented historical cases. The tool is candid that this is the same
evidentiary standard used by established operational indices (such as INFORM
Severity) in their early stages, and that a more rigorous, expert-panel-based
weighting exercise (using the Analytic Hierarchy Process, or AHP) is a planned
next step.

9.4 What the historical cases are for. The database of past operations is
used as a *reference check* on whether the tool's outputs align with the
retrospective consensus about how dangerous those situations were, not as a
statistical training set. The tool is explicit that no true statistical
"ground truth" exists for civilian evacuation decisions.

---

## 10. Limitations and Caveats

The prototype is unusually transparent about what it cannot do. Stated
limitations include:

10.1 It cannot read political intent. Sudden shifts in the behaviour of
warring parties, or the collapse of an agreement, are outside the model.

10.2 It is only as current as its inputs. Static entries cannot capture
rapidly changing battlefield conditions in real time.

10.3 It does not model armed-group behaviour or command fragmentation.

10.4 The historical dataset is small (a few dozen documented cases). This
is enough to sanity-check the framework but not enough for robust statistical
generalisation. CERAI is a *structured analytic framework, not a statistical
prediction model*.

10.5 Correlation is not causation. Alignment between inputs and past
outcomes does not prove a causal relationship.

10.6 It cannot always distinguish voluntary from coerced evacuation.

10.7 The weights are provisional, pending expert-panel validation.

Above all, the tool repeatedly states that its outputs are indicative and
are not a substitute for human judgment, legal expertise, or operational
assessment by qualified humanitarian and IHL professionals.

---

## 11. Practical Nature of the Tool

11.1 CERAI is delivered as a single self-contained web page that runs in an
ordinary web browser, with no installation required. It can be opened directly
or served locally, and it is published as a live public demonstration via
GitHub Pages.

11.2 Users can save "snapshots" of an assessment, export results, and load
pre-built example scenarios spanning moderate to extreme risk bands, making
the tool suitable for teaching, demonstration, and structured discussion.

---

## 12. Intended Audience and Use

12.1 CERAI is aimed at humanitarian coordinators, political
decision-makers, and legal reviewers, the people who must weigh whether and
how to move civilians, and who must be able to justify those decisions
afterward.

12.2 Its value is framed not as predictive accuracy but as decision
support: making reasoning visible, structured, reproducible, and open to
challenge. It is designed to complement, not replace, the expertise of ICRC
delegates, UN coordinators, and IHL practitioners.

---

## 13. Conclusion

13.1 CERAI represents a thoughtful attempt to bring structure and transparency
to one of the hardest categories of decision in armed conflict: whether, when,
and how to move civilians out of danger. Its most important contribution is
conceptual rather than technical. It insists on separating the *danger*
of remaining from the *possibility* of leaving, so that the legal duty to
protect civilians is never quietly overridden by operational difficulty.

13.2 The tool is deliberately modest about its status. It is a research
prototype, its weights are provisional, its dataset is small, and it is not
authorised for operational use without expert validation. But by making every
score traceable, every assumption visible, and every historical comparison
explicit, it offers a model for how automated tools can *support* humanitarian
and legal judgment responsibly, assisting human experts while keeping them
firmly in control of the decision.

---

## Attribution

Development advised by Teresa Cantero, PhD candidate in Spain, who is an alum of NYU Center for Global Affairs, as part of masters research on International Humanitarian Law and artificial intelligence (2026).


> Note: This report is a plain-language summary of a research prototype.
> The prototype is for academic demonstration only. Its outputs are indicative
> and are not a substitute for operational decision-making, legal advice, or
> assessment by qualified humanitarian and IHL professionals.
