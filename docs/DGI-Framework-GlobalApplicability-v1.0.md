> **⚠️ SUPERSEDED** — This document is superseded by [`GLOBAL-REGULATORY-EQUIVALENCE.md`](GLOBAL-REGULATORY-EQUIVALENCE.md), which provides the same regulatory mapping with additional detail. See [`INDEX.md`](INDEX.md).

# DGI Framework — Global Applicability v1.0

## International Regulatory Equivalence for Decision Governance Infrastructure

**Document ID:** DGI-GA-2026-002  
**Version:** 1.0  
**Date:** February 2026  
**Status:** Draft for Review  
**Purpose:** Demonstrate jurisdiction-neutral global applicability of DGI

---

## 1. Introduction

DGI is a jurisdiction-neutral specification. The 9 primitives are defined without reference to any specific regulation, making them applicable in **any legal system** that requires organizations to demonstrate decision accountability.

This document maps DGI primitives to regulatory requirements across **7 regulatory regions**, **23+ jurisdictions**, and **33+ regulatory frameworks**, demonstrating that DGI addresses a global need — not a European or American one.

---

## 2. Europe

| Regulation | Jurisdiction | Applicable Primitives | Decision Evidence Requirement |
|-----------|-------------|:---------------------:|------------------------------|
| **EU AI Act** (Reg. 2024/1689) | EU-27 | P1, P2, P3, P5, P6, P8 | Art. 12: automatic logging; Art. 13: transparency; Art. 14: human oversight; Art. 52: synthetic media disclosure |
| **GDPR** (Reg. 2016/679) | EU-27 + EEA | P2, P3, P4, P9 | Art. 22: safeguards for automated decisions; Art. 35: DPIA; Art. 44–50: cross-border transfers |
| **DORA** (Reg. 2022/2554) | EU financial entities | P1, P5, P9 | Art. 5: ICT risk management; Art. 11: resilience testing; Art. 17: incident reporting; Art. 28: third-party risk |
| **UK GDPR** + DPA 2018 | United Kingdom | P2, P3, P4, P9 | s.22: automated decision safeguards; ICO accountability framework |
| **FCA SM&CR** | UK financial sector | P1, P3, P5 | Senior manager accountability; decision audit trails |
| **Switzerland nFADP** (2023) | Switzerland | P4, P9 | Data protection; cross-border safeguards |
| **eIDAS** (Reg. 910/2014) | EU-27 | P1, P3, P7 | Art. 41: qualified timestamps; qualified electronic signatures |

---

## 3. Asia-Pacific

| Regulation | Jurisdiction | Applicable Primitives | Decision Evidence Requirement |
|-----------|-------------|:---------------------:|------------------------------|
| **China PIPL** (个人信息保护法, 2021) | China | P2, P3, P4, P9 | Art. 24: automated decision transparency; Art. 38–43: cross-border data transfer rules |
| **China DSL** (数据安全法) + **CSL** | China | P1, P5 | Data security review; critical infrastructure protection; data classification |
| **Japan APPI** (個人情報保護法, amended 2022) | Japan | P2, P4, P9 | Art. 41: proper handling obligations; Art. 24–26: cross-border provisions; PPC AI guidelines |
| **South Korea PIPA** (개인정보보호법, amended 2023) | South Korea | P2, P3, P9 | Art. 37-2: automated decision rights; cross-border transfer restrictions |
| **Singapore PDPA** + AI Verify | Singapore | P2, P5, P6 | Model AI Governance Framework 2.0; AI Verify testing toolkit; PDPA consent and accountability |
| **India DPDPA** (2023) | India | P2, P4, P9 | Sec. 11: automated decision rights; Data Protection Board; cross-border whitelisting |
| **Australia Privacy Act** (1988, amended) | Australia | P2, P3, P4 | APP 1: accountability; proposed AI regulation (2025 consultation); OAIC guidance |
| **Thailand PDPA** (2019) | Thailand | P2, P9 | Sec. 28: cross-border transfers; automated decision provisions |
| **Indonesia PDP Law** (2022) | Indonesia | P2, P4, P9 | Art. 10: automated decision rights; data localization requirements |
| **Taiwan PDPA** (amended 2023) | Taiwan | P2, P9 | Art. 10: automated decisions; cross-border restrictions |
| **Hong Kong PDPO** | Hong Kong SAR | P2, P4 | DPP 4: data security; PCPD ethical AI guidelines |

---

## 4. Americas

| Regulation | Jurisdiction | Applicable Primitives | Decision Evidence Requirement |
|-----------|-------------|:---------------------:|------------------------------|
| **US EO 14110** (2023) | United States (Federal) | P1, P2, P5, P6 | AI safety testing; red-teaming; federal agency reporting |
| **CCPA/CPRA** | US — California | P2, P3 | Automated decision opt-out; profiling restrictions; CPPA rulemaking |
| **NYC Local Law 144** (2023) | US — New York City | P6 | Mandatory bias audits for automated employment decisions |
| **Colorado AI Act** (SB 24-205) | US — Colorado | P2, P3, P5 | Algorithmic impact assessments; deployer duties; consumer rights |
| **HIPAA** | US — Healthcare | P1, P4, P5 | §164.312: technical safeguards; audit controls; integrity requirements |
| **SOX** / **Dodd-Frank** | US — Financial | P1, P3, P5 | Internal controls over financial reporting; whistleblower protections; audit trails |
| **GLBA** | US — Financial | P4, P5 | Safeguards Rule; privacy requirements for financial institutions |
| **Brazil LGPD** (Lei 13.709/2018) | Brazil | P2, P3, P9 | Art. 20: right to review automated decisions; ANPD enforcement and guidance |
| **Canada PIPEDA** + **AIDA** (C-27) | Canada | P2, P5, P6 | AIDA: AI system transparency obligations; PIPEDA: accountability principle; OPC guidance |

---

## 5. Middle East & Africa

| Regulation | Jurisdiction | Applicable Primitives | Decision Evidence Requirement |
|-----------|-------------|:---------------------:|------------------------------|
| **UAE AI Strategy 2031** + DIFC DP Law | UAE | P2, P5, P9 | National AI governance framework; DIFC data protection; ADGM RegTech framework |
| **Saudi Arabia PDPL** (2021) + SDAIA AI Ethics | Saudi Arabia | P2, P4, P9 | Personal data protection; AI ethics principles; Vision 2030 digital governance |
| **South Africa POPIA** (Act 4/2013) | South Africa | P2, P3, P4, P9 | Sec. 71: automated decision rights; Sec. 72: cross-border restrictions; Information Regulator |
| **Kenya Data Protection Act** (2019) | Kenya | P2, P9 | Automated decision provisions; data localization requirements |
| **Nigeria NDPR** (2019) / NDPA (2023) | Nigeria | P2, P4 | Data protection; automated decision provisions; NITDA enforcement |
| **Egypt Data Protection Law** (151/2020) | Egypt | P2, P9 | Automated processing provisions; cross-border transfer restrictions |

---

## 6. International Banking & Financial Standards

| Standard | Issuing Body | Applicable Primitives | Decision Evidence Requirement |
|----------|:------------:|:---------------------:|------------------------------|
| **BCBS 239** | Basel Committee (BIS) | P1, P4, P5 | Principle 1–6: risk data aggregation accuracy; reporting timeliness; data governance |
| **Basel III/IV** | Basel Committee (BIS) | P1, P3, P5 | Operational risk capital; model risk management (SR 11-7 equivalent); stress testing evidence |
| **FATF Recommendations** | FATF | P1, P2, P3 | Rec. 10–12: CDD decision records; Rec. 20: suspicious transaction reporting evidence; Rec. 15: new technologies |
| **MiFID II** | EU (ESMA) | P1, P3, P5 | Art. 16: organizational requirements; Art. 25: suitability records; algorithmic trading evidence |
| **PCI DSS 4.0** | PCI SSC | P1, P5, P7 | Req. 10: audit trails; Req. 12: security policies; cryptographic key management |
| **SWIFT CSP** | SWIFT | P1, P7 | Mandatory security controls; independent attestation requirements |
| **Solvency II** | EU (EIOPA) | P1, P3, P5 | Art. 41–49: governance system; risk management; internal audit evidence |

---

## 7. Primitive Universality Matrix

| Primitive | Europe | Asia-Pacific | Americas | Middle East / Africa | Banking / Financial | **Regions Covered** |
|-----------|:------:|:------------:|:--------:|:-------------------:|:-------------------:|:-------------------:|
| **P1** Discovery-Time Proof | ■ ■ ■ | ■ ■ | ■ ■ ■ | ■ | ■ ■ ■ ■ | **5/5** |
| **P2** Deliberation Capture | ■ ■ ■ | ■ ■ ■ ■ ■ ■ | ■ ■ ■ ■ | ■ ■ ■ ■ | ■ | **5/5** |
| **P3** Override Accountability | ■ ■ | ■ ■ | ■ ■ ■ ■ | ■ ■ | ■ ■ ■ | **5/5** |
| **P4** Continuity Memory | ■ ■ | ■ ■ ■ ■ | ■ ■ | ■ ■ ■ | ■ | **5/5** |
| **P5** Drift Detection | ■ ■ ■ | ■ ■ | ■ ■ ■ ■ | ■ | ■ ■ ■ ■ | **5/5** |
| **P6** Cognitive Bias Mitigation | ■ | ■ ■ | ■ ■ ■ | | | **3/5** |
| **P7** Quantum-Resistant Integrity | ■ | | | | ■ ■ | **2/5** |
| **P8** Synthetic Media Auth | ■ | | | | | **1/5** |
| **P9** Cross-Jurisdiction | ■ ■ ■ | ■ ■ ■ ■ ■ ■ | ■ ■ | ■ ■ ■ ■ | | **4/5** |

**Key finding:** Primitives P1–P5 and P9 are required across **all 5 regulatory regions**. P2 (Deliberation Capture) has the broadest mandate globally. This confirms decision evidence infrastructure is a **universal** requirement.

---

## 8. Jurisdictional Conflict Patterns

DGI's P9 addresses common cross-border regulatory conflicts:

| Conflict Pattern | Example Jurisdictions | Frequency |
|-----------------|----------------------|:---------:|
| Data localization vs. cross-border processing | China PIPL vs. GDPR; India DPDPA vs. CCPA | Very High |
| Automated decision opt-out rights | GDPR Art. 22 vs. US (no federal equivalent) | High |
| AI transparency requirements | EU AI Act vs. China (state security exemptions) | High |
| Retention periods | GDPR minimization vs. SOX 7-year; Basel III 5-year | High |
| Consent models | LGPD legitimate interest vs. PIPL explicit consent | Medium |
| AI bias audit mandates | NYC LL144 vs. jurisdictions with no requirement | Medium |

DGI defines **9 resolution strategies** applicable to any jurisdictional combination, including `highest_standard`, `jurisdiction_priority`, `data_localization`, `consent_overlay`, `contractual_safeguard`, `regulatory_exemption`, `good_faith_maximum`, `legal_opinion_based`, and `regulatory_sandbox`.

---

## 9. Language & Cultural Neutrality

DGI is designed for international adoption:

- **Jurisdiction-neutral primitive definitions** — no regulation-specific language in the 9 core definitions
- **Regulation-agnostic scoring** — IISS measures organizational capability, not compliance with specific laws
- **Configurable jurisdiction profiles** — organizations select applicable jurisdictions at deployment
- **Cultural sensitivity in bias detection** — P6 accounts for culture-specific bias patterns (e.g., authority bias varies by power-distance index per Hofstede/GLOBE frameworks)

---

## 10. Conclusion

DGI addresses decision evidence requirements present in **every major regulatory region worldwide**:

- **23+ jurisdictions** with explicit or emerging AI decision accountability requirements
- **33+ regulatory frameworks** mapped to DGI primitives
- **5 of 9 primitives** (P1–P5) relevant across all 5 regulatory regions
- **P9 (Cross-Jurisdiction)** specifically designed for multinational conflict resolution

**DGI is a global decision evidence infrastructure specification — not a regional compliance tool.**

---

*DGI Framework Global Applicability v1.0*
