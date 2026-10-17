# Reflective piece — draft v1 (evidence-grounded)

*Grounded in the actual portfolio artefacts: executive_summary_v2.md, tutor-feedback-and-response.md, pampered_pets_risk_identification_report.md. Short [CONFIRM] slots mark the only places needing your genuine experience — answer the numbered questions at the bottom and the slots fill in. Delete the italic note and this line before submission. Body measures 870 words as drafted (verified by count); expect ≈ 930–980 once the six [CONFIRM] slots are filled — still safely under the 1,000 cap.*

---

Reflecting on the Security and Risk Management module, and on the quantitative risk assessment for a digitalising business that concluded it, one question keeps resurfacing: can risk ever be known well enough to model, or does the act of quantification manufacture a confidence the underlying knowledge cannot support? This reflection works through that question in four stages, following Rolfe, Freshwater and Jasper's (2001) WHAT, SO WHAT and NOW WHAT structure: what the module's process and my contributions actually were; what working in a development team, and my own emotional responses, revealed; and what I now critique, and will do differently, as a risk practitioner.

The WHAT stage begins with the process itself. The final project required identifying and analysing security risks, threats and vulnerabilities for a firm moving to automated, international warehousing, then designing continuity arrangements for a 24/7/365 operation. I applied STRIDE threat modelling and attack trees to structure identification, selected Monte Carlo simulation decomposed along FAIR lines (Hubbard and Seiersen, 2023) after rejecting Bayesian updating and multi-criteria methods, and designed multi-region recovery on paired Azure regions. The intellectual frame was Aven and Thekdi's (2025) risk science: risk as knowledge about the world, graded by strength of knowledge, not merely measured in it. Not everything went to plan: my correlation assumption behaved differently in simulation than in intent, a friction that proved instructive.

My individual contribution ran on two tracks. Individually, I owned the executive summary end to end, including a reproducible Python model (200,000 iterations, fixed seed) and a substantial revision responding to eleven points of tutor feedback. In the Development Team Project, my Group 2 consultancy produced a risk identification report for Pampered Pets under ISO/IEC 27005:2022 [CONFIRM 1: which sections, register rows or research you personally owned].

The SO WHAT stage turns to the team. In the Pampered Pets exercise, the moment that stays with me was the team's treatment of the investor's three headline figures — 50% revenue uplift, 24% cost saving, 33% attrition — as claims to be tested rather than facts to be relayed [CONFIRM 2: a real moment of division of labour, disagreement or resolution you can describe first-hand]. What it revealed is that risk communication is less about transmitting findings than about negotiating what counts as evidence: Sutton (2021) argues qualitative estimation is defensible precisely where historical loss data is absent, and our group had to agree on that defensibility before any register row could be scored. The lesson generalises: technical and commercial audiences disagree not about the numbers but about what the numbers are entitled to claim.

My emotional responses were equally instructive. The model's output genuinely surprised me: cyber-attack, at a 17.4% annual frequency, accounted for 74.2% of the variance in aggregate annual loss, so a mid-table scenario dominated the tail — a result I had to sit with before trusting it. Working under the October deadline produced a familiar pressure to declare the model finished. [CONFIRM 3: how you actually felt at these moments — surprise, anxiety, defensiveness — and whether it changed the quality or timing of your work.] The tutor's provisional grade of 60% initially provoked defensiveness, which faded once the feedback proved to be eleven specific, checkable items rather than a general judgement; the emotion, once reframed, became information.

The NOW WHAT stage is the critique. My own approach over-trusted fluency: I had written that minimum, modal and maximum inputs were "assumed behind every input" without printing them, and had mentioned a fixed seed without supplying it. The marker read both exactly right — a promise in prose is not a deliverable, and reproducibility must live in the artefact, not beside it. Aven and Thekdi's (2025) strength-of-knowledge grading, and the cautionary principle it underwrites, changed how I think: every figure I now produce states what the judgement rests on. I do differently: I write for the reader of the document, not the author of the work, and I self-review against verifiability rather than fluency.

Professionally, the module developed quantitative literacy, critical analysis, and the communication of technical findings to non-technical audiences — the executive summary had to answer royalty and an investor in 2,000 words — alongside legal and ethical awareness of UK GDPR transfer rules and DPIAs [CONFIRM 4: how these map to your current role]. My next steps are concrete: apply structured risk decomposition to a live register in my current role by [CONFIRM 5: date]; adopt a reproducibility checklist (inputs, seed, assumptions printed in the artefact) for every analysis I deliver within the next quarter; and complete the top PDP action in my skills matrix by [CONFIRM 6: date].

In conclusion, the module made me a particular kind of risk practitioner: one who treats quantification as structured judgement rather than measurement, who states openly what each figure rests on, and who regards an unverified-looking claim as a defect in itself. The introduction's question resolves accordingly — risk cannot be known well enough to model with certainty, but it can be modelled honestly, and honesty is the controllable part. The reflective habit I will keep is Rolfe's simplest discipline: asking what happened, so what, and now what, until the last answer is checkable (Rolfe, Freshwater and Jasper, 2001; University of Edinburgh, no date).

## References

Aven, T. and Thekdi, S. (2025) *Risk Science: An Introduction*. 2nd edn. Abingdon: Routledge. Available at: https://doi.org/10.4324/9781003494317

Hubbard, D.W. and Seiersen, R. (2023) *How to Measure Anything in Cybersecurity Risk*. 2nd edn. Hoboken, NJ: Wiley.

Rolfe, G., Freshwater, D. and Jasper, M. (2001) *Critical reflection for nursing and the helping professions: a user's guide*. Basingstoke: Palgrave Macmillan.

Sutton, D. (2021) *Information Risk Management*. 2nd edn. Swindon: BCS Learning & Development.

University of Edinburgh (no date) *Reflection Toolkit*. Available at: https://reflection.ed.ac.uk/ (Accessed: 17 October 2026).

---

## The six confirmations needed from you

1. **Team contribution (¶3):** which parts of the Pampered Pets report did you personally draft — methodology, register rows, which assessment, references?
2. **Team moment (¶4):** one real moment — a disagreement, a division-of-labour decision, or how your group reached a decision. The investor-figures paragraph is written from the report; if you have a first-hand moment, it goes here.
3. **Emotions (¶5):** how you actually felt when the model surprised you / under deadline pressure / at the 60% provisional grade — one or two honest sentences.
4. **Current role (¶7):** your job context, so the transfer claims land on something real.
5. **Next-step dates (¶7):** a realistic date for applying risk decomposition at work, and for the top PDP action.
6. **Anything wrong:** confirm the deadline (12 October for Unit 11 delivery) and the 60% provisional grade match your records.
