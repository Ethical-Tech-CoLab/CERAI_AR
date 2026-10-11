# Decision-model recommendation: research-source checking only

Date: 2026-10-11. Public-source proposal, not operational or legal advice.
Reviewed [README](https://github.com/Ethical-Tech-CoLab/CERAI_AR/blob/3f6051506cca4b3a82e6b26c6b8b41e5340a57e7/README.md).
This is document-level assessment; the prototype was not scientifically validated.

## Recommendation

Keep weighted indicators, composite arithmetic, sensitivity analysis,
source-freshness records and existing confidence semantics unchanged.
Consider only a pre-analysis public-source relevance/support checker for a
researcher: supports / contradicts / not established / insufficient evidence.

Do not use a decision model to decide evacuation timing, legal compliance,
route safety, vulnerability priority or probability of harm. A score named
confidence is not automatically a calibrated safety probability.

## Evaluation

Compare human/checklist review and deterministic quote/date checks with local
classifiers, Jev's [citation recipe](https://docs.typesafe.ai/cookbooks/citation_check.md),
Microsoft-Decision-1 and Sage on permissioned public material.
The repository states reuse restrictions; reading a source does not grant
permission to redistribute its contents or send them to another service.

Split by event/source/time. Include stale weather, incompatible geographic
units, missing observations and claims extending beyond an index's scope.
Measure false reassurance, evidence recall, calibration and human-review
burden, with complete accepted-record cost.

## Gate

Offline derived annotations only; no changed inputs, model weights, formulas
or application conclusions. Human research review remains necessary. Exact
proprietary checkpoints are not locally offered; alternative local models need
their own evaluation. No accuracy or cost result is claimed.
