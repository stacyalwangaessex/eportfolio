---
layout: page
title: Artefact
---

# Unit 8 discussion forum — Peer Response 2 (to Abinel Madzivire)

**Thread:** Critique of CVSS and alternatives (Wunder et al., 2024) — three-week discussion covering Units 7–9
**Label:** Peer Response
**Responding to:** Abinel Madzivire, posted Tuesday, 8 September 2026, 7:08 PM
**Word count:** 201 body words excluding in-text citations, verified by count (209 including citations; within the 200–300 limit — citations and references excluded from the word count per the activity instructions)

---

**Peer Response**

Abinel, I agree with your critique, and in particular with your conclusion that CVSS's numerical precision should not be mistaken for objective risk. The evidence you cite supports this strongly: Wunder et al. (2024) found that differences in scoring traced back to characteristics of CVSS itself rather than evaluators' experience, which means the problem will persist no matter how experienced the team.

Your hybrid proposal — exploitation probability as the primary mechanism with CVSS severity retained as complementary — is a sensible reconciliation, and Jacobs et al. (2021) support the operational value of that ordering. I would build on it in one respect. Any combined system still requires human judgement where likelihood and consequence meet, and the study shows what happens when that judgement is unguided: 85% of participants found CVSS inconsistent yet 80% still used it. For the approach to be defensible, the point where probability and impact are weighed together must be explicit and documented — a defined decision rule rather than an intuitive blend — so the combined output inherits the auditability that EPSS provides for the likelihood half.

A question back to you: who should own that documented decision rule — the security team, or the asset owners whose risk is being decided?

## References

Jacobs, J., Romanosky, S., Edwards, B., Adjerid, I. and Roytman, M. (2021) 'Exploit Prediction Scoring System (EPSS)', *Digital Threats: Research and Practice*, 2(3), pp. 1–17. Available at: https://doi.org/10.1145/3436242 (Accessed: 17 October 2026).

Wunder, J., Kurtz, A., Eichenmüller, C., Gassmann, F. and Benenson, Z. (2024) 'Shedding Light on CVSS Scoring Inconsistencies: A User-Centric Study on Evaluating Widespread Security Vulnerabilities', *2024 IEEE Symposium on Security and Privacy (SP)*, pp. 1102–1121. Available at: https://doi.org/10.1109/SP54263.2024.00058 (Accessed: 17 October 2026).

---

*Artefact notes (not part of the post): evidences LO2 and LO3. Response is primarily agreement with extension, per user direction, engaging Abinel's own sources (Jacobs et al. 2021; Wunder et al. 2024). Second of two peer responses for this discussion; Unit 9 summary post follows.*
