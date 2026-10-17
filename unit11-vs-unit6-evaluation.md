# Evaluation: Final project (Unit 11) vs status document (Unit 6)

*Weighted at 5% (Collaboration). Compares the Group 2 Development Team Project status document (Unit 6) with the individual final project executive summary (Unit 11). Word count ≈ 380 body words.*

## What the status document set out (Unit 6)

The Unit 6 status document — the Group 2 risk identification report for Pampered Pets ([team-exercises/pampered_pets_risk_identification_report.md](team-exercises/pampered_pets_risk_identification_report.md)) — assessed both the status quo and the proposed digitalisation of a four-person micro-enterprise. It adopted ISO/IEC 27005:2022 with a qualitative five-point likelihood-and-impact matrix, explicitly justified on Sutton's (2021) argument that qualitative estimation suits contexts lacking historical loss data. Its recommendations were conditional rather than binary: proceed with digitalisation incrementally, establish a Phase 1 security baseline before any customer-facing system went live, and dual-source strategic suppliers to reduce key-supplier reliance. It also declined to accept the investor's three headline figures — 50% revenue uplift, 24% cost saving, 33% attrition — as stated.

## What the final project delivered (Unit 11)

The final project addressed a larger brief — a business moving to automated, international warehousing — and delivered a quantitative executive summary ([unit-11/executive_summary_v2.md](unit-11/executive_summary_v2.md)): STRIDE threat modelling and attack trees feeding a FAIR-structured Monte Carlo simulation of 200,000 iterations with a fixed seed, six risk scenarios with annual probabilities and percentile loss figures, sensitivity analysis, and an active–active multi-region continuity design meeting a sub-minute RTO and RPO.

## What changed between the two, and why

The method changed because the brief changed: the Unit 11 client requested probabilities and loss distributions, which a five-point matrix cannot supply, so qualitative screening gave way to Monte Carlo simulation with declared assumptions. Two substantive findings carried across. First, the Unit 6 concern about supplier concentration was vindicated: the model found key-supplier dependency the most probable single loss, at approximately 21% annual probability — precisely the failure mode the status document's dual-sourcing recommendation targeted. Second, the dominant risk shifted with scale: phishing, the top concern at micro-enterprise scale in Unit 6, was superseded at enterprise scale by cyber-attack on warehouse operational technology, which drove roughly three-quarters of the variance in aggregate annual loss. The principle that security precedes functionality also survived: the Phase 1 baseline became a recommendation to complete a DPIA before any new automated location.

## What this comparison taught me about project estimation

The status document worked as a baseline for measuring drift, not as a promise: the method did not survive contact with the new brief, but the risk judgements did — qualitative screening correctly ranked the concerns the quantitative model later confirmed. The transferable lesson is that scale changes the risk profile, so risk artefacts must be re-derived for each context rather than transplanted.

---

*Artefact notes: evidences the Collaboration criterion (5%) — evaluation of the final project against the midpoint status document, with specific figure anchors from both documents.*
