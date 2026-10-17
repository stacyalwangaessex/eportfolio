---
layout: page
title: Artefact
---

**Pampered Pets: Risk Identification Report**

An Assessment of the Status Quo and of the Proposed Digital
Transformation

Security and Risk Management (SRM_PCOM7E) --- Development Team Project,
Group 2

*Word count: 898 (main body; excludes title block, risk register tables,
figure and reference list)*

**1. Introduction**

Pampered Pets is a micro-enterprise: four staff, two networked
computers, a single wireless gateway shared with personal smartphones,
and ninety per cent of trade conducted face to face. Its new investor
proposes digitalisation and international sourcing. This report assesses
the risks of both the status quo and the proposed transformation,
interrogates the three growth propositions put to the consultancy, and
recommends a proportionate course of action.

**2. Risk Assessment Methodology**

ISO/IEC 27005:2022 has been adopted for both assessments. It is guidance
rather than a certifiable requirement, and so scales to a four-person
firm without imposing the documentation burden of a full management
system (ISO, 2022). Three further considerations informed the selection:

- Continuity: it aligns with ISO/IEC 27001 and ISO 31000, so controls
  selected now remain valid should international trading later oblige
  the business to seek certification.

- Fitness for purpose: its asset-based identification approach suits an
  organisation whose critical assets are few and tangible --- recipes,
  supplier relationships, transaction records and brand reputation.

- Rejected alternatives: NIST SP 800-30 is oriented towards US federal
  systems, while OCTAVE Allegro presumes internal analytical capacity
  that Pampered Pets does not possess (Kirvan, 2021).

A qualitative five-point likelihood and impact matrix is applied
throughout, following Sutton\'s (2021) argument that qualitative
estimation suits contexts lacking historical loss data. Alice is the
risk owner; appetite is low for regulatory risk and moderate for
commercial risk.

**3. Assessment 1: The Business As It Stands**

**3.1 Context and vulnerabilities**

- A flat, unsegmented wireless network carries the point-of-sale
  terminal, the warehouse computer and personal smartphones alike.

- The warehouse machine is described as old and is therefore probably
  beyond vendor support and unpatched.

- There is no stated backup regime, multi-factor authentication, written
  policy or incident plan; the survivability of the business rests on
  four individuals.

This posture is typical rather than exceptional: only 30% of UK
businesses conducted a cyber risk assessment last year, and among micro
businesses just 31% held a formal policy and 14% delivered any staff
training (Department for Science, Innovation and Technology and Home
Office, 2026). Typicality, however, is not a defence.

**3.2 Risk and threat evaluation**

  -----------------------------------------------------------------------------------
  **Risk / threat             **Threat      **Likelihood**   **Impact**   **Rating**
  scenario**                  source**                                   
  ------------------------ --------------- ---------------- ------------ ------------
  R1 Phishing or business   Cybercriminal         4              4         **High**
  email compromise diverts                                               
  orders                                                                 

  R2 Ransomware disables    Cybercriminal         3              4         **High**
  the unsupported                                                        
  warehouse computer                                                     

  R3 Lateral movement from   Criminal /           4              3         **High**
  personal devices onto        insider                                   
  the flat network                                                       

  R4 Irrecoverable data      Accidental           3              5         **High**
  loss (no verified                                                      
  backup)                                                                

  R5 UK GDPR breach or       Regulatory           3              3        **Medium**
  unevidenced                                                            
  accountability                                                         

  R6 Customer migration to     Market             4              4         **High**
  online competitors                                                     
  -----------------------------------------------------------------------------------

*Table 1: Risk register --- current state (likelihood and impact scored
1--5).*

Phishing was the most prevalent attack type experienced by UK businesses
(38%) and was judged most disruptive by 69% of those breached, while
ransomware fell to 1% (DSIT and Home Office, 2026). R1 and R3 therefore
warrant priority over more dramatic scenarios. R6 is deliberately
included: Sørensen (2018) frames digitalisation as both opportunity and
risk; on that reading, inaction is itself a risk decision.

**3.3 Proposed mitigations**

- Implement automated cloud backup with a tested restore; isolate or
  retire the unsupported warehouse machine.

- Segregate the network into business and staff/guest SSIDs and enforce
  multi-factor authentication on email and banking.

- Adopt a concise acceptable-use and incident-response policy, with
  quarterly phishing briefings for all four staff.

- Map the personal data held, register with the ICO and apply a
  retention schedule to satisfy the accountability principle
  (Information Commissioner\'s Office, 2026).

- Adopt the five Cyber Essentials control areas as a proportionate
  benchmark (National Cyber Security Centre, no date).

**4. Assessment 2: The Digitalisation Programme**

**4.1 Proposed changes**

- An e-commerce storefront using a hosted payment page, so that no
  cardholder data is stored locally.

- A cloud inventory system replacing the warehouse spreadsheet and
  integrating with the point of sale.

- Email marketing and a blog to widen reach.

- Onboarding of international suppliers and third-party logistics.

**4.2 Risk and threat evaluation**

  -------------------------------------------------------------------------------------
  **Risk / threat             **Threat      **Likelihood**   **Impact**    **Rating**
  scenario**                  source**                                   
  ------------------------ --------------- ---------------- ------------ --------------
  D1 Web skimming or        Cybercriminal         4              5        **Critical**
  formjacking of the                                                     
  checkout page                                                          

  D2 Payment fraud and       Criminal /           3              4          **High**
  loss of PCI DSS            regulatory                                  
  validation                                                             

  D3 Wider personal data     Regulatory           4              4          **High**
  processing and overseas                                                
  transfers                                                              

  D4 Compromise or outage   Supply chain          3              4          **High**
  of platform or logistics                                               
  provider                                                               

  D5 Loss of local           Operational          4              5        **Critical**
  provenance and                                                         
  ten-minute contingency                                                 

  D6 Capability gap: four       Human             4              3          **High**
  staff absorbing new                                                    
  systems                                                                
  -------------------------------------------------------------------------------------

*Table 2: Risk register --- post-digitalisation.*

ENISA attributes about 60% of observed initial access to phishing, and
records supply chain as 10.6% of threat categories (ENISA, 2025). D1 is
rated critical because merchants must now confirm that their site is not
susceptible to attacks from scripts affecting their e-commerce systems
to remain eligible for the simplified Self-Assessment Questionnaire A
(PCI Security Standards Council, 2025). D5 warrants particular emphasis:
the claimed 24% saving is a gross unit-cost figure ignoring freight,
tariffs, quality assurance and the loss of a supply chain that staff can
currently rescue by car. Only 12% of micro businesses review supplier
risk (DSIT and Home Office, 2026), so digitalisation would convert a
resilient local dependency into a fragile, unmonitored global one.

**4.3 Proposed mitigations**

- Fully outsource card handling to a compliant provider, obtain its
  Attestation of Compliance and validate through SAQ A.

- Deploy Content Security Policy and Subresource Integrity, and schedule
  quarterly external vulnerability scanning.

- Complete a data protection impact assessment before launch; put
  processor contracts, a privacy notice and marketing consent in place.

- Dual-source: retain local suppliers for signature product lines and
  audit international suppliers before any switch.

- Retain a managed security provider, as 44% of micro businesses already
  do, and cost cyber insurance into the business case.

**5. Recommendations and Conclusion**

The team recommends proceeding with digitalisation, but incrementally
and with the Phase 1 security baseline established before any
customer-facing system goes live. None of the three figures put to us
should be accepted as stated. A 50% uplift in revenue is plausible only
across several years and only if fulfilment capacity grows with demand.
The 24% saving is optimistic once total cost of ownership and lost
resilience are counted. The 33% attrition figure is unevidenced, but its
direction is credible, and it is the strongest argument against the
status quo.

  -------------------------------------------------------------------------------------------------------------------------------
  **Workstream**   **M1**   **M2**   **M3**   **M4**   **M5**   **M6**   **M7**   **M8**   **M9**   **M10**   **M11**   **M12**
  ---------------- -------- -------- -------- -------- -------- -------- -------- -------- -------- --------- --------- ---------
  Phase 1 --                                                                                                            
  Security                                                                                                              
  baseline                                                                                                              

  Phase 2 --                                                                                                            
  E-commerce & PCI                                                                                                      
  DSS                                                                                                                   

  Phase 3 -- Cloud                                                                                                      
  inventory system                                                                                                      

  Phase 4 --                                                                                                            
  Staged                                                                                                                
  international                                                                                                         
  sourcing                                                                                                              

  Continuous --                                                                                                         
  Training & risk                                                                                                       
  review                                                                                                                
  -------------------------------------------------------------------------------------------------------------------------------

*Figure 1: Indicative twelve-month implementation timeline.*

The status quo is not the low-risk option; it merely relocates risk from
the technical domain to the commercial one, where it is less visible and
harder to reverse. Digitalisation is therefore recommended, conditional
on security controls preceding functionality, local sourcing being
preserved for the products on which the brand\'s reputation rests, and
the assessment being revisited at each phase gate.

**Reference List**

Department for Science, Innovation and Technology and Home Office (2026)
*Cyber security breaches survey 2025/2026*. Available at:
https://www.gov.uk/government/statistics/cyber-security-breaches-survey-20252026/cyber-security-breaches-survey-20252026
(Accessed: 30 August 2026).

ENISA (2025) *ENISA threat landscape 2025*. Available at:
https://enisa.europa.eu/publications/enisa-threat-landscape-2025
(Accessed: 30 August 2026).

Information Commissioner\'s Office (2026) *A guide to the data
protection principles*. Available at:
https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-protection-principles/a-guide-to-the-data-protection-principles
(Accessed: 30 August 2026).

International Organization for Standardization (2022) *ISO/IEC
27005:2022 Information security, cybersecurity and privacy protection
--- Guidance on managing information security risks*. Geneva: ISO.
Available at: https://www.iso.org/standard/80585.html (Accessed: 30
August 2026).

Kirvan, P. (2021) *Top 15 IT security frameworks and standards
explained*. Available at:
https://www.techtarget.com/searchsecurity/tip/IT-security-frameworks-and-standards-Choosing-the-right-one
(Accessed: 30 August 2026).

National Cyber Security Centre (no date) *Cyber Essentials*. Available
at: https://www.ncsc.gov.uk/cyberessentials/overview (Accessed: 30
August 2026).

PCI Security Standards Council (2025) *Important updates announced for
merchants validating to Self-Assessment Questionnaire A*. Available at:
https://blog.pcisecuritystandards.org/important-updates-announced-for-merchants-validating-to-self-assessment-questionnaire-a
(Accessed: 30 August 2026).

Sørensen, B.T. (2018) \'Digitalisation: An Opportunity or a Risk?\',
*Journal of European Competition Law & Practice*, 9(6), pp. 349-350.
Available at: https://doi.org/10.1093/jeclap/lpy038

Sutton, D. (2021) *Information Risk Management*. 2nd edn. Swindon: BCS
Learning & Development.
