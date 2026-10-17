# Executive Summary

## 1. Purpose and scope

Cathy is moving the business to a fully digital operating model: an international supply chain served by automated warehouses worldwide. Two prospective clients — HRH the King and Prince Albert II of Monaco — have raised the same objection: whether these changes put product quality or security of supply at risk. This summary estimates the probability of such damage, sets out continuity and disaster-recovery arrangements keeping the shop running 24/7/365 with recovery objectives under one minute, and states openly where estimates rest on judgement rather than measurement.

Risk follows Aven and Thekdi (2025, chapter 2): the consequences of an activity with attached uncertainties, (C,U), or (A,C,U) with an initiating event identified. Their descriptive scheme (A′,C′,Q,K) — what is considered, how uncertain, on what knowledge (Aven and Thekdi, 2025, chapter 3) — runs through the analysis, so every figure states what the judgements rest on.

## 2. Identifying the risks

Risk sources, threats and hazards were identified before quantification, following the core text's process (Aven and Thekdi, 2025, chapter 4): a STRIDE-based threat model of the warehousing and e-commerce estate — STRIDE asks how a system might be attacked, not only how it might fail (OWASP, 2024) — and attack trees decomposing the most serious threat, warehouse disruption, into pathways.

Two clusters emerged. The first is quality: automation removes part of the tacit judgement on which a luxury producer relies; the failure modes are sensor drift, calibration error, cold-chain excursion in transit, and loss of craft oversight once production spreads across sites. The second is supply: international dispersal enlarges the attack surface and multiplies single points of failure; the risks are key-supplier dependency, logistics congestion, ransomware against operational technology, and data corruption between connected systems. Quality maps to integrity and supply to availability in the CIA triad, so the analysis tracks those dimensions rather than confidentiality.

## 3. Selecting a method, and its limitations

Monte Carlo simulation was chosen, structured by the FAIR decomposition of risk into loss-event frequency and magnitude (Hubbard and Seiersen, 2023). It returns the probabilities and loss distributions the clients asked for, copes with the thin incident record of a new model, and supports the sensitivity analysis that shows which variables drive the result.

The weaknesses: results are only as good as the distributions supplied, so weak elicitation produces output that looks precise while being unreliable; the method is demanding computationally and in the statistical literacy it assumes; and treating variables as independent flatters the model whenever they move together. Section 4 addresses these by publishing the full inputs, seed and correlation term, though no design removes them. Two alternatives were rejected: Bayesian updating, valuable once real incident data accumulates but less transparent for the threshold-based questions posed here; and multi-criteria methods such as AHP and TOPSIS (Taherdoost and Madanchian, 2023), which collapse judgements into a preference score and yield no loss distributions.

## 4. Assumptions and data

- **Simulation and reproducibility:** 200,000 iterations with NumPy's PCG64 generator and a fixed seed of 42, so every figure regenerates from the supplied model file ([poc_execsummary_mc_c8f2.py](poc_execsummary_mc_c8f2.py)). Frequency is Poisson with rate λ = −ln(1 − p), reproducing the elicited annual probability p; per-event severity is lognormal, with the quoted minimum and maximum as its 5th and 95th percentiles and dispersion σ (Table 1).
- **Quality risk:** modelled assumptions reflecting the Section 2 failure modes, magnitude as the share of annual revenue exposed to rework, recall or reputational damage.
- **Supply risk:** modelled assumptions informed by sector-survey incident patterns (BCI, 2023; PwC, 2023): survey-wide rates supplied upper-bound logic, scaled down to sanity-check the assumed frequencies' plausibility for a firm of this size; they were not treated as measured probabilities.
- **Correlation:** cyber-attack and logistics-disruption frequencies are joined by a Gaussian copula with latent correlation ρ = 0.55, chosen to give a rank correlation near 0.3 between the event counts, reflecting their coincidence in peak trading; it leaves each Poisson marginal as elicited; Section 5 reports the correlation achieved.
- **Horizon and limitation:** all magnitudes are EUR over one year; where no internal data existed, informed judgement stood in for measurement, widening the uncertainty around the results.

**Table 1. Elicited model inputs.** p = assumed annual probability of at least one event; severity is lognormal with the stated median and dispersion σ.

| Risk scenario | Annual p | λ | Min (5th pct, €) | Most likely (median, €) | Max (95th pct, €) | σ |
|---|---|---|---|---|---|---|
| Quality: cold-chain or sensor failure | 6.4% | 0.066 | 252,956 | 800,000 | 2,530,088 | 0.70 |
| Quality: loss of craft oversight | 11.2% | 0.119 | 130,454 | 350,000 | 939,028 | 0.60 |
| Supply: cyber-attack or ransomware | 17.5% | 0.192 | 375,532 | 1,400,000 | 5,219,257 | 0.80 |
| Supply: key-supplier dependency failure | 21.0% | 0.236 | 202,338 | 500,000 | 1,235,558 | 0.55 |
| Supply: logistics or congestion disruption | 14.8% | 0.160 | 223,635 | 600,000 | 1,609,762 | 0.60 |
| Supply: data-integrity corruption | 9.6% | 0.101 | 149,090 | 400,000 | 1,073,175 | 0.60 |

## 5. Results

Tables 2 and 3 report the per-scenario and aggregate measures. The simulated frequencies reproduce the elicited probabilities of Table 1 to within 0.1 percentage points — evidence that the copula did not disturb the marginals.

**Table 2. Simulated results per scenario (200,000 iterations, seed 42).**

| Risk scenario | P(≥1 loss event in one year) | 95th-percentile loss | 99th-percentile loss |
|---|---|---|---|
| Quality: cold-chain or sensor failure | 6.3% | €458,874 | €1,676,000 |
| Quality: loss of craft oversight | 11.3% | €399,453 | €856,143 |
| Supply: cyber-attack or ransomware | 17.4% | €2,427,801 | €5,452,225 |
| Supply: key-supplier dependency failure | 21.0% | €838,967 | €1,496,789 |
| Supply: logistics or congestion disruption | 14.8% | €835,658 | €1,630,922 |
| Supply: data-integrity corruption | 9.6% | €402,139 | €907,842 |

**Table 3. Aggregate measures across all six scenarios.**

| Aggregate measure | Value |
|---|---|
| P(any quality-loss event in one year) | 16.9% |
| P(any supply-disruption event in one year) | 46.7% |
| P(any loss event across all scenarios) | 55.7% |
| Mean annual loss | €784,736 |
| Aggregate 95th-percentile annual loss | €3,334,441 |
| Aggregate 99th-percentile annual loss | €6,390,119 |
| Quality scenarios: aggregate 95th / 99th percentile | €755,755 / €1,809,920 |
| Supply scenarios: aggregate 95th / 99th percentile | €3,108,566 / €6,197,860 |

Mean annual loss is about €0.78m, but the 99th-percentile combined loss reaches €6.39m — a strongly right-skewed aggregate driven by correlated cyber-and-logistics events. Sensitivity was computed on the aggregate distribution: each scenario's variance share is the covariance of its simulated annual loss with the aggregate, divided by the aggregate variance — cyber-attack dominates at 74.2%, logistics disruption follows at 10.8%, cold-chain failure 6.0%, supplier dependency 5.7%, and data-integrity corruption and craft oversight under 2% each. The realised Spearman rank correlation between the cyber-attack and logistics event counts, 0.32, sits close to the 0.3 target.

Where inputs rest on judgement, the output reflects present belief of only moderate strength of knowledge (Aven and Thekdi, 2025, chapter 5); the value lies less in exact percentages than in uncertainty made visible and comparable, so spending is justified against a transparent rationale, not intuition.

### 5.1 The digital model compared with the previous operating model

The claim that digitalisation does not inherently threaten quality must be argued against the model it replaces — one that concentrated production at a single site, where quality rested on manual inspection and craft judgement and short transit and a concentrated supplier base kept exposures small. The digital model disperses production, lengthens the cold chain and enlarges the supplier base — and the model attributes both quality exposures to those decisions, not the automation: cold-chain excursion (6.3% of years) tracks transit distance, and loss of craft oversight (11.3%) the spread of production across sites. Automation adds detection the previous model lacked: continuous monitoring and tamper-evident logging shorten undetected excursions. On the supply side the contrast is sharper: supplier dependency (21.0%) follows from international scale, not digitalisation, while cyber-attack (17.4%) is the one genuinely new risk class the digital model introduces — and the largest driver of aggregate variance.

The qualification matters as much as the claim: both models use the same judgement-based inputs, and no measured loss record exists for the previous one, so the comparison is argued, not measured. With moderate confidence, digitalisation adds one new dominant risk while adding detection against quality loss; a definitive comparison needs the previous model quantified once real incident data accumulates.

## 6. Recommendations, in order of commercial priority

Recommendations are ranked by commercial exposure, starting with the greatest threat to revenue and client confidence.

**Priority 1. Harden the supply chain against cyber-attack (17.4% annual frequency; 74.2% of aggregate variance).** Warehouse operational technology should be segregated from corporate networks, with segmentation, least privilege and continuous monitoring (NIST, 2024) — the largest probability-weighted loss and the clients' voiced concern.

**Priority 2. Reduce key-supplier dependency (21.0%).** Dual-sourcing of critical components addresses the most likely single failure mode yet is the control most often deferred on cost grounds (Christopher, 2016); given the probabilities, deferral is difficult to defend.

**Priority 3. Protect quality control under automation (16.9% aggregate quality frequency).** Human quality gates should sit alongside automated sensing, with the cold chain instrumented for tamper-evident logging — the defence closest to what the clients pay for, underpinning Section 5.1.

**Priority 4. Data-integrity controls (9.6%).** Reconciliation and referential-integrity checks will stop erroneous data propagating silently between connected systems.

**Priority 5. Standards and GDPR compliance (a critical business requirement).** Moving personal data across an international supply chain engages the restrictions on transfers to third countries under the UK and EU GDPR (Regulation (EU) 2016/679, 2016; Data Protection Act 2018). A Data Protection Impact Assessment should be mandatory at each new automated site, with Standard Contractual Clauses or an adequacy decision for cross-border processing and the ISO 31000 and NIST frameworks structuring assurance (ISO, 2018; NIST, 2024). Concentrating sensitive data across automated warehouses deepens the firm's duty of care, so commercial, legal and ethical pressures must be balanced, not optimised for one.

## 7. Business continuity and disaster recovery

A business continuity plan begins with a business impact assessment (Wallace and Webber, 2017), from which the governing parameters derive: a recovery time objective (RTO) and recovery point objective (RPO), both under one minute — the changeover window. Values this tight rule out ordinary backup-and-restore, which recovers in hours.

**Platform choice.** I recommend Microsoft Azure, deployed across UK South (primary) and UK West (secondary), a documented Azure region pair (Microsoft, 2026c). Both regions sit in one jurisdiction, keeping data residency defensible under Section 6's transfer rules; their infrastructure is deliberately separate, so they can fail independently; and Microsoft staggers maintenance across pairs. Azure offers published recovery figures closest to the one-minute objectives and failover machinery managed rather than hand-built.

**Named services.** Azure Front Door terminates customer traffic at the global edge, probes each regional origin and shifts traffic to the healthy region when probes fail (Microsoft, 2026d). Azure Kubernetes Service hosts the shop front end and APIs, zone-redundant across availability zones. Azure SQL Database Business Critical holds transactional data, zone-redundant across three availability zones with synchronous replication; an auto-failover group links it to a UK West secondary, with listener endpoints that survive a geo-failover (Microsoft, 2026a).

**What the design delivers, and what it does not.** For loss of a single availability zone, synchronous replication gives a published RPO of zero and RTO typically under 30 seconds (Microsoft, 2026a): both objectives are met. For loss of an entire region, replication is asynchronous: the published typical failover RTO remains under 60 seconds, but the published RPO is "equal to or greater than zero", depending on transactions not yet replicated when the outage struck (Microsoft, 2026a), so a sub-minute RPO cannot be guaranteed regionally. A Microsoft-managed failover policy also waits out a grace period — no lower than one hour — before forcing a failover, since confirming a region is down takes human judgement (Microsoft, 2026b); a customer-managed policy lets the firm fail over deliberately once operators confirm it.

```
                       Customers and shop traffic
                                   |
                    Azure Front Door (global anycast);
                    health probes drive origin failover
                          /                   \
        UK South (primary)          UK West (secondary, paired region)
                 |                           |
      AKS zone-redundant           AKS zone-redundant
      (shop front end, APIs)       (shop front end, APIs)
                 |                           |
  Azure SQL Database Business  auto-    Azure SQL Database Business
  Critical, zone-redundant:    failover Critical, zone-redundant:
  3 availability zones,        group    3 availability zones,
  synchronous replication      (async)  synchronous replication
  zonal failure: RPO 0,                 zonal failure: RPO 0,
  RTO typically <30 s                   RTO typically <30 s

  Regional failover across the pair: RTO typically <60 s; RPO bounded by
  replication lag, so the sub-minute RPO holds for zonal failures only.
```

*Figure 1. Multi-region recovery architecture on Azure: zone-redundant high availability within each region, with an auto-failover group between UK South and UK West.*

**Testing and acceptance criteria.** A design this dependent on automation fails quietly if never exercised; the core text lists drills among the instruments of resilience management (Aven and Thekdi, 2025, chapter 8). Quarterly drills force a zonal failover and a geo-failover in turn, with measured RTO and RPO logged against the objectives and breaches escalated; an annual game day simulates a full UK South outage; and replication-lag monitoring keeps the regional RPO exposure known, not assumed. Vendor lock-in: proprietary services raise the cost of exit over time (Opara-Martins, Sahandi and Tian, 2016); infrastructure-as-code, containerisation and open formats mitigate but do not remove it, so an exit test is funded annually rather than portability assumed.

## 8. Conclusion

The modelling suggests digitalisation does not inherently threaten product quality: aggregate quality-loss probability is 16.9%, its drivers are dispersal and transit rather than automation, and automation adds detection the previous model lacked. It does raise supply-chain disruption, to 46.7% for at least one event a year, dominated by supplier dependency (21.0%) and cyber-attack (17.4%), the latter alone accounting for 74.2% of the variance in annual loss. These figures rest on judgement-based inputs of moderate strength of knowledge, and the comparison with the previous operating model is argued, not measured: they should inform the decision, not make it. The sequence is cyber hardening first, dual-sourcing second, quality gates third, data-integrity controls fourth, with GDPR-compliant transfers built in from the outset. The continuity design — Azure across UK South and UK West, zone-redundant within each region and linked by an auto-failover group — meets the one-minute objectives for zonal failures by published figures and the RTO regionally, states the regional RPO gap openly, and is proven by quarterly drills and an annual game day. That gives the firm a defensible answer for its premium clients, aligned with a risk landscape where automation and artificial intelligence keep reshaping threats and defences (Aven and Thekdi, 2025, chapter 12; Dwivedi *et al.*, 2021).

## References

Aven, T. and Thekdi, S. (2025) *Risk Science: An Introduction*. 2nd edn. Abingdon: Routledge. Available at: https://doi.org/10.4324/9781003494317

BCI (2023) *BCI Supply Chain Resilience Report 2023*. Available at: https://www.thebci.org/static/340ffa9b-03b4-4baf-9add7071cbbea758/BCI-Supply-Chain-Resilience-Report-2023.pdf (Accessed: 11 October 2026).

Christopher, M. (2016) *Logistics and Supply Chain Management*. 5th edn. Harlow: Pearson.

*Data Protection Act 2018*, c. 12. United Kingdom. Available at: https://www.legislation.gov.uk/ukpga/2018/12/contents/enacted (Accessed: 11 October 2026).

Dwivedi, Y.K. *et al.* (2021) 'Artificial Intelligence (AI): multidisciplinary perspectives on emerging challenges, opportunities, and agenda for research, practice and policy', *International Journal of Information Management*, 57, 101994. Available at: https://doi.org/10.1016/j.ijinfomgt.2019.08.002

Hubbard, D.W. and Seiersen, R. (2023) *How to Measure Anything in Cybersecurity Risk*. 2nd edn. Hoboken, NJ: Wiley.

ISO (2018) *ISO 31000:2018 Risk management — Guidelines*. Geneva: International Organization for Standardization. Available at: https://www.iso.org/standard/65694.html (Accessed: 11 October 2026).

Microsoft (2026a) *Business continuity and disaster recovery — Azure SQL Database*. Microsoft Learn. Available at: https://learn.microsoft.com/en-us/azure/azure-sql/database/business-continuity-high-availability-disaster-recover-hadr-overview (Accessed: 17 October 2026).

Microsoft (2026b) *Failover groups overview & best practices — Azure SQL Database*. Microsoft Learn. Available at: https://learn.microsoft.com/en-us/azure/azure-sql/database/failover-group-sql-db (Accessed: 17 October 2026).

Microsoft (2026c) *Azure region pairs and nonpaired regions*. Microsoft Learn. Available at: https://learn.microsoft.com/en-us/azure/reliability/regions-paired (Accessed: 17 October 2026).

Microsoft (2026d) *Health probes — Azure Front Door*. Microsoft Learn. Available at: https://learn.microsoft.com/en-us/azure/frontdoor/health-probes (Accessed: 17 October 2026).

NIST (2024) *The NIST Cybersecurity Framework (CSF) 2.0*. Gaithersburg, MD: National Institute of Standards and Technology. Available at: https://doi.org/10.6028/NIST.CSWP.29

Opara-Martins, J., Sahandi, R. and Tian, F. (2016) 'Critical analysis of vendor lock-in and its impact on cloud computing migration: a business perspective', *Journal of Cloud Computing*, 5, 4. Available at: https://doi.org/10.1186/s13677-016-0054-z

OWASP (2024) *Threat Modeling Cheat Sheet*. Available at: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html (Accessed: 11 October 2026).

PwC (2023) *Global Digital Trust Insights 2024*. Available at: https://www.pwc.com/hu/hu/kiadvanyok/assets/pdf/pwc-2024-global-digital-trust-insights.pdf (Accessed: 11 October 2026).

*Regulation (EU) 2016/679 of the European Parliament and of the Council of 27 April 2016 on the protection of natural persons with regard to the processing of personal data and on the free movement of such data (General Data Protection Regulation)* (2016) *Official Journal* L 119, 4 May, pp. 1–88. Available at: https://eur-lex.europa.eu/eli/reg/2016/679/oj (Accessed: 11 October 2026).

Taherdoost, H. and Madanchian, M. (2023) 'Multi-criteria decision making (MCDM) methods and concepts', *Encyclopedia*, 3(1), pp. 77–87. Available at: https://doi.org/10.3390/encyclopedia3010006

Wallace, M. and Webber, L. (2017) *The Disaster Recovery Handbook*. 3rd edn. New York: AMACOM.