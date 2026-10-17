---
layout: page
title: Artefact
---

# Unit 10 — Practical Applications and Issues in DR Implementations

**Unit topic:** Practical disaster recovery design: the impact of RPO and RTO values on DR solutions, typical system solutions for standby requirements, DRaaS advantages and disadvantages, and the challenges of vendor lock-in, resilience and network security.

## Artefact(s)

- The DR design that answers this unit's outcomes directly: [Executive summary §7, Business continuity and disaster recovery](../unit-11-individual-project/executive_summary_v2.html)
- [CONFIRM: add any Unit 10 seminar/lab DR-design output if one was produced]

## Link to learning outcomes

Executive summary §7 was written against this unit's outcome set. A sub-minute RTO and RPO, extracted from the client's stated changeover window and data-loss tolerance via a Business Impact Assessment (Wallace and Webber, 2017), ruled out standard backup-and-restore designs; an active–active multi-region architecture with synchronous replication and automated health-check-driven failover was designed to meet them. The unit's critical themes are addressed head-on: DRaaS versus self-managed infrastructure is weighed on capital and operating expenditure against ceded control; vendor lock-in is treated honestly (exit costs rise even under infrastructure-as-code, so a periodic exit test is funded rather than portability assumed, following Opara-Martins, Sahandi and Tian, 2016); and network security is designed in, because replication propagates a compromised state as readily as a healthy one. The paired-region placement constraint closes the loop with the GDPR obligations covered in Units 5–6.

## References

Opara-Martins, J., Sahandi, R. and Tian, F. (2016) 'Critical analysis of vendor lock-in and its impact on cloud computing migration: a business perspective', *Journal of Cloud Computing*, 5, 4. Available at: https://doi.org/10.1186/s13677-016-0054-z (Accessed: 11 October 2026).

Wallace, M. and Webber, L. (2017) *The Disaster Recovery Handbook*. 3rd edn. New York: AMACOM.
