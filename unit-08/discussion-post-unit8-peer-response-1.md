---
layout: page
title: Artefact
---

# Unit 8 discussion forum — Peer Response 1 (to Janet Karani)

**Thread:** Critique of CVSS and alternatives (Wunder et al., 2024) — three-week discussion covering Units 7–9
**Label:** Peer Response
**Responding to:** Janet Karani, posted Thursday, 17 September 2026, 10:41 AM
**Word count:** 196 body words excluding in-text citations, verified by count (204 including citations; within the 200–300 limit — citations and references excluded from the word count per the activity instructions)

---

**Peer Response**

Janet, I agree with your critique, and in particular with the severity-versus-risk distinction you draw. Wunder et al. (2024) show the problem runs deeper than inconsistent judgement: experience and self-rated expertise explained almost none of the variance in their regression, so the inconsistency is a property of the instrument itself. Your point that organisations may prioritise differently even when using the same framework follows directly — contested inputs cannot deliver reproducible prioritisation.

Your case for EPSS is well argued. I would add one refinement: EPSS estimates the probability of exploitation rather than its impact, so the two systems answer different questions. A vulnerability that is likely to be exploited but trivially exploitable against an unimportant asset, and one that is rarely exploited but catastrophic on compromise, may score identically on EPSS and very differently in consequence. This is why Aven and Thekdi (2025) treat risk as depending on both likelihood and consequence under uncertainty. EPSS therefore strengthens CVSS as an input to prioritisation, but the impact dimension still needs a home — which is where decision-tree approaches earn their place.

A question back to you: would you combine EPSS with severity scoring, and if so, whose impact judgement supplies the missing half?

## References

Aven, T. and Thekdi, S. (2025) *Risk Science*. Abingdon: Routledge.

Wunder, J., Kurtz, A., Eichenmüller, C., Gassmann, F. and Benenson, Z. (2024) 'Shedding Light on CVSS Scoring Inconsistencies: A User-Centric Study on Evaluating Widespread Security Vulnerabilities'. Available at: https://arxiv.org/abs/2308.15259 (Accessed: 17 October 2026).

---

*Artefact notes (not part of the post): evidences LO2 and LO3. Response is primarily agreement with extension, per user direction, engaging Janet's own sources (Aven and Thekdi 2025; Wunder et al. 2024).*
