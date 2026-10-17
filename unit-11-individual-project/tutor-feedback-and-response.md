---
layout: page
title: Artefact
---

# Unit 11 — tutor feedback and my response

*Required portfolio element: "Feedback from peers and tutors". The provisional grade for the Unit 11 executive summary was 60% (19/30 knowledge, 17/30 criticality, 13/20 sources, 5/10 structure, 6/10 integrity). The feedback below is summarised from the marker's comments; my response shows how each point was addressed in the revised artefact ([executive_summary_v2.md](executive_summary_v2.md)).*

## What the marker said, and what I did about it

| # | Feedback point | My response | Where |
|---|----------------|-------------|-------|
| 1 | The submission promised minimum, modal and maximum inputs without providing them; calculations were insufficiently explained. | I added a full input table (annual probabilities, severity medians and dispersions for all six scenarios), explained the Poisson-rate conversion λ = −ln(1 − p), and documented the lognormal severity fitting. | v2 §4 |
| 2 | The recovery proposal needed named services and a definite platform recommendation. | The revised artefact names a definite platform (Microsoft Azure, paired UK South and UK West regions) and specific services (Azure Front Door, Azure SQL Database Business Critical zone-redundant, auto-failover groups), with the decision rationale. | v2 §7 |
| 3 | Sensitivity contributions and correlation assumptions lacked supporting calculations. | I now state how variance shares are computed (covariance of each scenario's simulated annual loss with the aggregate, divided by aggregate variance) and report both the target and achieved correlation (ρ = 0.55 latent; Spearman 0.32 realised). | v2 §4–5 |
| 4 | An aggregate supply-disruption probability was missing. | Added: 46.7% probability of at least one supply-disruption event per year, alongside the 16.9% quality figure. | v2 §5 |
| 5 | The conclusion that digitalisation does not inherently threaten quality was not established against the previous operating model. | I added an explicit comparison with the previous craft-based, single-site model, and qualified the conclusion honestly: the inputs are judgement-based, so the comparison is argued, not measured. | v2 §5 |
| 6 | Recovery claims needed clearer qualification and testing criteria. | The revised design separates zonal failures (synchronous replication; published RPO 0 / RTO ≤ 60 s) from full regional outages (asynchronous; RPO ≤ 5 min), states the qualification openly, and sets test criteria: quarterly failover drills with measured RTO/RPO, an annual regional game day, and a funded annual exit test. | v2 §7 |
| 7 | Scaling of survey findings into company-specific probabilities was not demonstrated. | §4 now states explicitly how sector surveys were used: to sanity-check the plausibility of the assumed frequencies (upper-bound logic, scaled by firm size), not to derive them, and the limitation is restated. | v2 §4 |
| 8 | Direct technical documentation was needed for replication, regional configuration and failover performance. | Added Microsoft Learn technical references for zone redundancy, auto-failover groups and their published RTO/RPO figures. | v2 §7 + references |
| 9 | Fixed seed mentioned but not supplied, limiting reproducibility. | The seed value (42, NumPy PCG64) and iteration count (200,000) are now stated in the artefact itself, and the model file is linked so any figure can be regenerated. | v2 §4 |
| 10 | Author names and citation formatting needed consistent checking. | A consistency pass was run over all in-text citations against the reference list; every citation maps to exactly one entry and vice versa. | v2 references |
| 11 | Misplaced commas, awkward sentences, repetition; a recovery diagram would help. | The revised artefact was proofread line by line, repetition was cut, and a text-based recovery architecture diagram was added. | v2 throughout, §7 |

## What this feedback taught me (reflection prompts, for the ≤1,000-word piece)

- **Reproducibility must live in the artefact, not beside it.** I knew the model was seeded and reproducible, but the reader of the document alone could not verify that. "Mentioned but not supplied" is a reproducibility failure. Lesson: evidence belongs where the reader is, not where the work was done.
- **A promise in prose is not a deliverable.** Writing "assumed minimum, most-likely and maximum values behind every input" without printing them created the appearance of rigour without its substance — the marker read it exactly right.
- **Self-assessment optimism.** I over-estimated this work against the rubric. The gap was concentrated in specific, checkable items (inputs, seed, platform decision, aggregate probability) rather than general quality — which suggests my self-review was checking for the wrong things: fluency instead of verifiability.
- **Proofreading is a graded skill, not a courtesy.** The structure band (5/10) shows how much presentation errors cost in a 10% criterion.