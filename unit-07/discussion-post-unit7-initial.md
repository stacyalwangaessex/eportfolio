# Unit 7 discussion forum — Initial Post (CVSS discussion, Units 7–9)

**Thread:** Critique of CVSS and alternatives (Wunder et al., 2024) — three-week discussion covering Units 7–9
**Label:** Initial Post
**Word count:** 203 body words excluding in-text citations, verified by count (216 including citations)

---

**Initial Post**

Wunder et al. (2024) criticise three characteristics of CVSS. First, inconsistency: for widespread vulnerability types such as Out-of-bounds Write and Cross-site Scripting, the Attack Vector, User Interaction and Scope metrics were scored inconsistently by 196 professional users, and 68% of follow-up participants scored the same vulnerability differently nine months later. Second, the treatment of security deficiencies: non-exploitable weaknesses such as Missing HTTPOnly Flag were rated across a broad severity range, although CVSS should return None where no damage occurs. Third, the documentation: rarely consulted, dispersed across three documents, and ambiguous for precisely the difficult cases. I agree with this critique. Consistency was not rescued by experience — regression showed personal factors explained little variance — which locates the fault in the instrument itself, consistent with Spring et al.'s (2021) argument that the Base Score formula is neither empirically nor theoretically justified and is routinely misused as a risk score.

Of the alternatives discussed, I argue SSVC (Spring et al., 2020) should replace CVSS. It is a decision tree that asks the question practitioners actually face — how urgently must this be remediated — rather than computing a spurious decimal from contested metrics. It is transparent, stakeholder-specific, and sidesteps precisely the metrics Wunder et al. (2024) found unscorable, while remaining auditable when stakeholder preferences differ.

## References

Spring, J.M., Hatleback, E., Householder, A., Manion, A. and Shick, D. (2021) 'Time to Change the CVSS?', *IEEE Security & Privacy*, 19(2), pp. 74–78.

Spring, J., Hatleback, E., Householder, A., Manion, A. and Shick, D. (2020) *Prioritizing Vulnerability Response: A Stakeholder-Specific Vulnerability Categorization (Version 1.1)*. Workshop on the Economics of Information Security.

Wunder, J., Kurtz, A., Eichenmüller, C., Gassmann, F. and Benenson, Z. (2024) 'Shedding Light on CVSS Scoring Inconsistencies: A User-Centric Study on Evaluating Widespread Security Vulnerabilities'. Available at: https://arxiv.org/abs/2308.15259 (Accessed: 17 October 2026).

---

*Artefact notes (not part of the post): evidences LO2 (critical synthesis of research) and LO3 (evaluation of vulnerability management methods). Peer responses follow in Unit 8; summary post in Unit 9.*
