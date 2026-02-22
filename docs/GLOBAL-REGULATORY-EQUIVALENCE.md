# Global Regulatory Equivalence

**Document Type:** ISO New Work Item Proposal — International Applicability  
**Version:** 1.0 | February 2026  
**Purpose:** Demonstrate that DGI is globally relevant, not euro/US-centric

---

## 1. Introduction

DGI is designed as a jurisdiction-neutral specification. While regulatory examples in the framework reference EU and US frameworks (as the most mature AI governance regimes), the 9 primitives are applicable to **any jurisdiction** that requires organizations to demonstrate decision accountability.

This document maps DGI primitives to regulatory requirements across **7 regulatory regions** and **23 jurisdictions**, demonstrating global applicability.

---

## 2. Regional Regulatory Mapping

### 2.1 Europe

| Regulation | Jurisdiction | DGI Primitives | Evidence Requirement |
|-----------|-------------|:--------------:|---------------------|
| **EU AI Act** (Reg. 2024/1689) | EU 27 | P1, P2, P3, P5, P6, P8 | Art. 12: logging; Art. 13: transparency; Art. 14: human oversight; Art. 52: synthetic media |
| **GDPR** (Reg. 2016/679) | EU 27 + EEA | P2, P3, P4, P9 | Art. 22: automated decision safeguards; Art. 35: DPIA; Art. 44–50: international transfers |
| **DORA** (Reg. 2022/2554) | EU financial sector | P1, P5, P9 | Art. 5: ICT risk; Art. 11: testing; Art. 17: incident reporting |
| **UK GDPR** + DPA 2018 | United Kingdom | P2, P3, P4, P9 | s.22 automated decisions; ICO accountability framework |
| **FCA Rules** (SYSC 8, SM&CR) | UK financial sector | P1, P3, P5 | Senior manager accountability; decision audit trails |
| **Switzerland nFADP** | Switzerland | P4, P9 | Data protection; cross-border transfer safeguards |

### 2.2 Asia-Pacific

| Regulation | Jurisdiction | DGI Primitives | Evidence Requirement |
|-----------|-------------|:--------------:|---------------------|
| **China PIPL** (个人信息保护法) | China | P2, P3, P4, P9 | Art. 24: automated decision-making transparency; Art. 38–43: cross-border transfers |
| **China CSL** (网络安全法) + **DSL** (数据安全法) | China | P1, P5 | Data security review; critical information infrastructure protection |
| **Japan APPI** (個人情報保護法) | Japan | P2, P4, P9 | Art. 41: proper handling; Art. 24–26: cross-border provisions; PPC guidelines on AI |
| **South Korea PIPA** (개인정보보호법) | South Korea | P2, P3, P9 | Art. 37-2: automated decision rights; Art. 28: cross-border restrictions |
| **Singapore PDPA** + **AI Verify** | Singapore | P2, P5, P6 | Model AI Governance Framework; AI Verify testing framework; PDPA consent requirements |
| **India DPDPA** (2023) | India | P2, P4, P9 | Sec. 11: automated decisions; Data Protection Board oversight; cross-border whitelisting |
| **Australia Privacy Act** (1988, amended) | Australia | P2, P3, P4 | APP 1: accountability; proposed AI regulation (2025 consultation) |
| **Thailand PDPA** (2019) | Thailand | P2, P9 | Sec. 28: cross-border transfers; automated decision provisions |
| **Indonesia PDP Law** (2022) | Indonesia | P2, P4, P9 | Art. 10: automated decision rights; data localization requirements |
| **Taiwan PDPA** (amended 2023) | Taiwan | P2, P9 | Art. 10: automated decisions; cross-border transfer restrictions |
| **Hong Kong PDPO** | Hong Kong SAR | P2, P4 | DPP 4: data security; voluntary AI ethics guidelines |

### 2.3 Americas

| Regulation | Jurisdiction | DGI Primitives | Evidence Requirement |
|-----------|-------------|:--------------:|---------------------|
| **US EO 14110** (2023) | United States (Federal) | P1, P2, P5, P6 | AI safety testing; red-team requirements; federal agency reporting |
| **CCPA/CPRA** | US — California | P2, P3 | Automated decision-making opt-out; profiling restrictions |
| **NYC Local Law 144** | US — New York City | P6 | Bias audits for automated employment decisions |
| **Colorado AI Act** (2024) | US — Colorado | P2, P3, P5 | Algorithmic impact assessments; deployer duties |
| **HIPAA** | US — Healthcare | P1, P4, P5 | §164.312: technical safeguards; audit controls; integrity |
| **SOX** / **Dodd-Frank** | US — Financial | P1, P3, P5 | Internal controls; whistleblower protections; audit trails |
| **Brazil LGPD** (Lei 13.709) | Brazil | P2, P3, P9 | Art. 20: automated decision review rights; ANPD enforcement |
| **Canada PIPEDA** + **AIDA** (proposed) | Canada | P2, P5, P6 | AIDA: AI system transparency; PIPEDA: accountability principle |

### 2.4 Middle East & Africa

| Regulation | Jurisdiction | DGI Primitives | Evidence Requirement |
|-----------|-------------|:--------------:|---------------------|
| **UAE AI Strategy 2031** + **DIFC DP Law** | UAE | P2, P5, P9 | National AI governance; DIFC data protection; Abu Dhabi ADGM framework |
| **Saudi Arabia PDPL** (2021) + **SDAIA AI Ethics** | Saudi Arabia | P2, P4, P9 | Data protection; AI ethics principles; Vision 2030 digital governance |
| **South Africa POPIA** (Act 4 of 2013) | South Africa | P2, P3, P4, P9 | Sec. 71: automated decisions; Sec. 72: cross-border restrictions; Information Regulator enforcement |
| **Kenya Data Protection Act** (2019) | Kenya | P2, P9 | Automated decision rights; data localization |
| **Nigeria NDPR** (2019) | Nigeria | P2, P4 | Data protection; automated decision provisions |

### 2.5 International Banking & Financial Standards

| Standard | Scope | DGI Primitives | Evidence Requirement |
|----------|-------|:--------------:|---------------------|
| **BCBS 239** (Basel Committee) | Global banking | P1, P4, P5 | Risk data aggregation; reporting accuracy; data governance |
| **Basel III / Basel IV** | Global banking | P1, P3, P5 | Operational risk; model risk management (SR 11-7 equivalent) |
| **FATF Recommendations** | Global AML/CFT | P1, P2, P3 | Rec. 10–12: CDD decision records; Rec. 20: suspicious transaction reporting evidence |
| **MiFID II** | EU financial markets | P1, P3, P5 | Art. 16: organizational requirements; Art. 25: suitability assessment records |
| **PCI DSS 4.0** | Global payment systems | P1, P5, P7 | Req. 10: audit trails; Req. 12: security policies; cryptographic requirements |
| **SWIFT CSP** | Global banking messaging | P1, P7 | Mandatory security controls; attestation requirements |

---

## 3. Primitive Universality Analysis

Every DGI primitive maps to requirements in **multiple jurisdictions across multiple regions**:

| Primitive | Europe | Asia-Pacific | Americas | Middle East/Africa | Banking/Financial |
|-----------|:------:|:------------:|:--------:|:-----------------:|:-----------------:|
| **P1** Discovery-Time Proof | ■ ■ ■ | ■ ■ | ■ ■ ■ | ■ | ■ ■ ■ ■ |
| **P2** Deliberation Capture | ■ ■ ■ | ■ ■ ■ ■ ■ ■ ■ | ■ ■ ■ ■ ■ | ■ ■ ■ ■ | ■ |
| **P3** Override Accountability | ■ ■ | ■ ■ | ■ ■ ■ ■ | ■ ■ | ■ ■ |
| **P4** Continuity Memory | ■ ■ | ■ ■ ■ ■ | ■ ■ | ■ ■ ■ | ■ |
| **P5** Drift Detection | ■ ■ ■ | ■ ■ | ■ ■ ■ | ■ | ■ ■ ■ ■ |
| **P6** Cognitive Bias Mitigation | ■ | ■ ■ | ■ ■ ■ | | |
| **P7** Quantum-Resistant Integrity | | | | | ■ ■ |
| **P8** Synthetic Media Auth | ■ | | | | |
| **P9** Cross-Jurisdiction | ■ ■ ■ | ■ ■ ■ ■ ■ ■ | ■ ■ | ■ ■ ■ ■ | |

**Key finding:** P2 (Deliberation Capture) and P5 (Drift Detection) are the most universally required primitives — relevant across all 5 regulatory regions. This confirms that decision evidence infrastructure is a **global** need, not a regional one.

---

## 4. Jurisdictional Conflict Resolution

DGI's P9 (Cross-Jurisdiction Compliance) is specifically designed for multinational organizations operating under conflicting regulatory regimes:

### 4.1 Common Conflicts

| Conflict | Jurisdictions | DGI Resolution |
|----------|--------------|---------------|
| Data localization vs. cross-border processing | China PIPL Art. 38 vs. GDPR Art. 44 | P9 documents conflict, generates good-faith maximum-compliance strategy |
| Automated decision opt-out rights | EU GDPR Art. 22 vs. US (no federal equivalent) | P9 applies highest-standard strategy across operations |
| AI transparency requirements | EU AI Act Art. 13 vs. China (state security exemptions) | P9 documents irreconcilable conflict with legal opinion |
| Retention periods | GDPR minimization vs. SOX 7-year retention | P9 jurisdiction-priority strategy per data category |
| Consent models | LGPD legitimate interest vs. PIPL explicit consent | P9 consent-overlay strategy |

### 4.2 Resolution Strategies (ISO-relevant)

DGI defines 9 resolution strategies applicable across any jurisdictional combination:

1. **highest_standard** — Apply the most restrictive requirement globally
2. **jurisdiction_priority** — Apply local law where operations occur
3. **data_localization** — Process locally, synchronize metadata
4. **consent_overlay** — Obtain consent meeting all applicable thresholds
5. **contractual_safeguard** — SCCs, BCRs, or equivalent instruments
6. **regulatory_exemption** — Document applicable exemptions with evidence
7. **good_faith_maximum** — Document maximum-achievable compliance with rationale
8. **legal_opinion_based** — Formal legal opinion with liability acceptance
9. **regulatory_sandbox** — Operate under sandbox provisions where available

---

## 5. Language and Cultural Neutrality

DGI is designed for international adoption:

- **No jurisdiction-specific terminology** in the 9 primitive definitions
- **Regulation-agnostic scoring** — IISS measures organizational capability, not compliance with specific laws
- **Configurable jurisdiction profiles** — organizations select applicable jurisdictions
- **Multi-language evidence export** — Regulator's Receipt™ supports localized output
- **Cultural sensitivity** — bias detection library includes culture-specific bias patterns (e.g., authority bias varies significantly between high/low power-distance cultures per Hofstede's framework)

---

## 6. Conclusion

DGI addresses decision evidence requirements that exist in **every major regulatory regime worldwide**. The 9 primitives are jurisdiction-neutral by design, with P9 (Cross-Jurisdiction Compliance) specifically addressing the multinational coordination challenge.

**DGI is not a European or American standard — it is a global decision evidence infrastructure specification.**

---

*Decision Governance Infrastructure — Datacendia, LLC*
