# Datacendia Decision Governance Infrastructure (DDGI)

## A Vendor-Neutral Framework for Institutional Decision Accountability

---

### Title Page

**Datacendia Decision Governance Infrastructure (DDGI)**
A Vendor-Neutral Framework for Institutional Decision Accountability

Primary Author: Stuart Rainey
Published by: Datacendia LLC
Publication Year: 2026

This framework is published as a conceptual contribution to institutional governance, decision accountability, and auditability architecture.

---

## Document Status

| Field | Value |
|-------|-------|
| **Status** | Candidate (self-published, not independently reviewed) |
| **Type** | Normative framework specification |
| **Version** | 1.0 |
| **Last Updated** | February 2026 |
| **Scope** | Vendor-neutral decision governance primitives |
| **Relationship** | DCII (in `README.Implementation.md`) is the Datacendia-branded reference implementation |

> **Note:** This document defines a vendor-neutral framework. Datacendia-specific implementation details, product names, and commercial features are documented separately in `README.Implementation.md`. Where Datacendia-branded language appears in this document, it serves as a reference example, not a normative requirement.

---

## Standards-Style Front Matter

### Abstract

Datacendia Decision Governance Infrastructure (DDGI) defines a vendor-neutral framework for treating institutional decisions as auditable lifecycle artifacts. The framework introduces governance primitives enabling organizations to preserve procedural integrity, decision provenance, and evidentiary continuity under scrutiny. DDGI complements existing governance and compliance systems — including risk management (ISO 31000:2018), records management (ISO 15489-1:2016), and AI management systems (ISO/IEC 42001:2023) — by operationalizing decision traceability without prescribing specific technologies. While adjacent standards address risk treatment, information security, and AI system lifecycle management, none define a structured evidence infrastructure for the decision act itself (see Section 7).

### Scope

This framework applies to institutional decision environments where auditability, accountability, and reconstruction capability are required, consistent with the governance objectives of ISO 37000:2021 (Governance of organizations) and the accountability principles of the OECD AI Principles (2019). It is implementation-agnostic and suitable for public or private sector governance contexts.

### Audience

* governance architects
* compliance leaders
* institutional risk professionals
* standards contributors
* system designers

---

## Publication Metadata

Framework Title: Datacendia Decision Governance Infrastructure (DDGI)
Author: Stuart Rainey
Publisher: Datacendia LLC
Version: 1.0
Publication Date: 2026
Document Type: Governance Framework
Intended Use: Conceptual and institutional reference

---

## Copyright and License

© 2026 Stuart Rainey. All rights reserved.

This framework is published for educational, institutional, and standards discussion purposes. Organizations may reference, adapt, or extend the framework with appropriate attribution.

No warranty is expressed or implied regarding regulatory compliance or implementation outcomes. Redistribution should preserve authorship attribution and framework integrity.

---

## Citation Format

Recommended citation:

Rainey, Stuart. *Datacendia Decision Governance Infrastructure (DDGI): A Vendor-Neutral Framework for Institutional Decision Accountability.* Datacendia LLC, 2026.

---

# Framework Body

### Section Type Guide

| Sections | Type | Meaning |
|----------|------|---------|
| §1–§7 (Problem, Principles, Primitives, Lifecycle, Artifacts, Maturity, Standards Mapping) | **Normative** | Defines the DDGI framework requirements |
| §8 (Framework Positioning, DCII Relationship) | **Informative** | Describes one reference implementation; not required for conformance |
| §9–§13 (Extensibility, Outcomes, Certification, Authorship, Standards Submission) | **Normative** | Framework governance and extensibility rules |

---

## Executive Overview

Modern institutions increasingly operate in environments where consequential decisions must withstand regulatory, legal, and adversarial scrutiny [1]. Despite investments in analytics and compliance tooling, many organizations lack formal structures for preserving the procedural lineage of decision formation. The EU AI Act (Regulation (EU) 2024/1689) and the NIST AI Risk Management Framework [2] both require demonstrable governance of AI-assisted decisions, yet neither prescribes a structured evidence architecture for the decision act itself.

Datacendia Decision Governance Infrastructure (DDGI) treats decisions as auditable lifecycle artifacts. The framework defines governance primitives enabling context capture, deliberation traceability, override accountability, evidence integrity, and drift detection — drawing on established principles from records management (ISO 15489-1:2016 [3]), risk management (ISO 31000:2018 [4]), and information security governance (ISO/IEC 27001:2022 [5]).

DDGI complements existing governance and risk frameworks by operationalizing decision provenance without mandating specific technical architectures.

---

## 1. Problem Definition

High-impact decisions often occur across distributed systems where documentation fragments over time [6]. Common institutional weaknesses include incomplete input capture, undocumented overrides, fragmented evidence trails, and post-hoc reconstruction based on memory. Research on organizational decision-making demonstrates that retrospective rationalization — the post-hoc reconstruction of reasoning — is a pervasive institutional risk (Kahneman, Sibony & Sunstein, 2021 [7]).

Existing governance standards address adjacent concerns: ISO/IEC 38507:2022 [8] provides guidance on the governance implications of IT, and ISO/IEC 23894:2023 [9] addresses AI risk management. However, neither defines a structured artifact model for preserving the procedural lineage of how decisions were formed, deliberated, and resolved.

DDGI addresses this governance gap by formalizing decision provenance and lifecycle preservation.

---

## 2. Framework Principles

DDGI is founded on four principles that extend the accountability and transparency requirements identified in ISO 37000:2021 [10] and the OECD Recommendation on AI (2019) [11]:

1. **Decisions as lifecycle artifacts** — Decisions are treated as first-class records with defined lifecycle phases, consistent with the records management principles of ISO 15489-1:2016 [3]
2. **Procedural integrity** — The process of decision formation is preserved with the same rigor as the decision outcome, addressing the "process verification" gap identified in AI audit research (Raji et al., 2020 [12])
3. **Evidence survivability** — Decision artifacts must survive organizational change, system migration, and adversarial scrutiny, extending the business continuity concepts of ISO 22301:2019 [13] to the decision domain
4. **Institutional continuity** — Governance knowledge persists beyond individual tenure, supporting the knowledge preservation objectives recognized in organizational learning literature (Argote & Miron-Spektor, 2011 [14])

---

## 3. Governance Primitives

DDGI defines five governance primitives. Each maps to a measurable institutional control and addresses a specific evidentiary requirement:

| Primitive | Name | Governance Question | Related Standards |
|-----------|------|---------------------|-------------------|
| A | **Context Capture** | What information was available at decision time? | ISO 15489-1 [3], EU AI Act Art. 12 |
| B | **Deliberation Traceability** | What alternatives were considered and why? | NIST AI RMF Map function [2] |
| C | **Override Accountability** | Who made the final decision and on what basis? | ISO/IEC 42001 A.8.4 [15], EU AI Act Art. 14 |
| D | **Evidence Integrity** | Can we prove the record has not been altered? | ISO/IEC 27001 A.8.10 [5], eIDAS Regulation |
| E | **Drift Detection** | Has the decision context or compliance posture changed since resolution? | ISO 31000 Clause 6.7 [4], NIST AI RMF Manage function [2] |

Each primitive corresponds to measurable institutional controls supporting auditability. The primitive set is intentionally minimal — covering the five irreducible evidentiary requirements for decision reconstruction — while remaining extensible for domain-specific needs (see Section 9).

---

## 4. Decision Lifecycle Architecture

Initiation → Deliberation → Resolution → Preservation → Reconstruction

Each lifecycle phase produces artifacts supporting verification and reconstruction.

### Decision Lifecycle Diagram

![Decision Lifecycle: Initiation → Deliberation → Resolution → Preservation → Reconstruction](docs/diagrams/decision-lifecycle.svg)

*Figure 1: The DDGI decision lifecycle. Each phase produces governance artifacts supporting verification and reconstruction.*

---

## 5. Evidence and Verification Model

Institutions maintain provenance metadata, contributor attribution, integrity safeguards, and reconstruction pathways. This approach aligns with the W3C PROV Data Model (PROV-DM) [16] for representing provenance information and extends it to the institutional decision domain.

Verification emphasizes procedural transparency over outcome defense — a distinction recognized in the algorithmic auditing literature (Metaxa et al., 2021 [17]). The evidentiary model supports both internal governance review and external regulatory inquiry, consistent with the dual-audience requirements identified in ISO/IEC TR 24028:2020 [18] (Overview of trustworthiness in artificial intelligence).

---

## 6. Governance Architecture Model

Institutional policy informs lifecycle execution. Governance primitives govern artifact generation and preservation. Evidence repositories enable audit and review functions.

### Governance Architecture Diagram

![Governance Architecture: Institutional Policy → Lifecycle Engine → Governance Primitives / Evidence Repository / Audit](docs/diagrams/governance-architecture.svg)

*Figure 2: The DDGI governance architecture. Institutional policy drives lifecycle execution; governance primitives generate artifacts preserved in evidence repositories for audit and review.*

---

## 7. Alignment with Existing Governance Structures

DDGI is designed to complement — not replace — existing governance standards. The following table maps DDGI primitives to adjacent standards, demonstrating non-duplication:

| Standard | Focus | DDGI Relationship |
|----------|-------|-------------------|
| **ISO 31000:2018** [4] | Risk management process | DDGI preserves evidence of how risk-informed decisions were made; ISO 31000 governs the risk assessment itself |
| **ISO 15489-1:2016** [3] | Records management | DDGI extends records management to the decision lifecycle; ISO 15489 provides the archival foundation |
| **ISO/IEC 42001:2023** [15] | AI management system | DDGI provides the decision evidence layer that ISO 42001 references but does not specify |
| **ISO/IEC 38507:2022** [8] | IT governance | DDGI operationalizes the accountability principles ISO 38507 establishes at the board level |
| **ISO/IEC 23894:2023** [9] | AI risk management | DDGI captures the decision artifacts that AI risk assessments produce; ISO 23894 governs the risk methodology |
| **NIST AI RMF** [2] | AI risk management | DDGI maps to Govern, Map, Measure, and Manage functions; provides the evidentiary substrate |
| **W3C DPV** [19] | Data privacy vocabulary | DDGI decision artifacts may reference DPV terms for privacy-relevant decisions; complementary vocabularies |

For a detailed gap analysis demonstrating non-duplication with 14 existing standards, see the companion document [ISO-GAPS-IN-EXISTING-STANDARDS.md](docs/ISO-GAPS-IN-EXISTING-STANDARDS.md).

---

## 8. Framework Positioning and Reference Implementation

> **Section type: Informative.** This section describes one reference implementation (DCII by Datacendia). It is not part of the normative framework specification. Other implementations may satisfy DDGI requirements independently.

DDGI is vendor-neutral. Implementations may operationalize primitives through diverse architectures. Reference implementations demonstrate realization without redefining framework semantics.

### 8.1 Relationship to DCII (Informative)

**The Decision Crisis Immunization Infrastructure (DCII) is the reference implementation of the DDGI framework.** The relationship is analogous to how HTTP (the protocol specification) relates to NGINX or Apache (server implementations), or how SQL (the language standard) relates to PostgreSQL (a database engine).

| | DDGI (Framework) | DCII (Reference Implementation) |
|---|---|---|
| **Nature** | Vendor-neutral specification | Production implementation |
| **Primitives** | 5 core governance primitives (A–E) | 9 measurable primitives (P1–P9), extending DDGI's 5 with 4 advanced capabilities |
| **Scoring** | Defines maturity index (DDGMI, 5 levels) | Implements IISS™ (0–1000 quantitative score) |
| **Technology** | Implementation-agnostic | PostgreSQL, REST API, cryptographic signing |
| **Audience** | Standards bodies, governance architects | Engineering teams, compliance implementers |
| **Artifacts** | Conceptual lifecycle model | JSON schemas, OpenAPI spec, database schemas |

DCII extends DDGI's five core primitives with four advanced capabilities — Cognitive Bias Mitigation (P6), Quantum-Resistant Integrity (P7), Synthetic Media Authentication (P8), and Cross-Jurisdiction Compliance (P9) — that address emerging governance requirements not yet covered by existing standards.

Organizations may implement DDGI through DCII or through independent implementations that satisfy the primitive requirements defined in this framework.

---

## 9. Framework Extensibility

Implementations may define additional domain-specific primitives while preserving core semantic integrity.

---

## 10. Institutional Outcomes

Adoption supports audit readiness, procedural transparency, reconstruction capability, and governance resilience.

---

## 11. Certification Considerations

Certification may evaluate lifecycle traceability, artifact preservation, and measurable controls. Certification indicates governance capability, not regulatory compliance.

---

## 12. Formal Authorship and Origin Statement

DDGI is published as an original governance framework establishing authorship of its structure and articulation while recognizing foundational governance principles in the public domain.

---

## 13. Standards Submission Considerations

The framework is structured for compatibility with ISO/IEC JTC 1/SC 42 (Artificial Intelligence) processes and may be submitted as a New Work Item Proposal (NP). The submission is supported by:

- **Gap analysis** demonstrating non-duplication with 14 existing ISO standards [8, 9, 15]
- **Global regulatory equivalence** mapping to 23 jurisdictions across 7 regions
- **Non-duplication proof** systematic comparison against ISO 42001, 38507, 23894, 31000, and NIST
- **Scope boundary definition** clarifying where DDGI stops and adjacent standards begin

DDGI targets the specific gap identified in the current standards landscape: no existing ISO standard defines a structured evidence infrastructure for the decision act itself. ISO 42001 requires organizations to "determine and apply criteria for AI decisions" (A.8.4) but does not prescribe how decision evidence is captured, preserved, or reconstructed.

---

# Legal and Attribution Sections

---

## Legal Disclaimer

This framework is conceptual guidance and does not constitute legal or regulatory advice. Institutions remain responsible for independent compliance evaluation.

---

## Attribution Statement

DDGI synthesizes established governance principles into an original framework architecture. Attribution preserves conceptual lineage.

---

## Non-Endorsement Clause

Publication does not imply endorsement by any standards body or regulatory authority.

---

## Framework Originality Statement

The architecture and terminology represent an original synthesis intended to support governance discourse.

---

## Publication Safe-Harbor Statement

The framework is published in good faith to encourage institutional accountability innovation. Implementation responsibility remains with adopting organizations.

---

# Appendices

---

## Appendix A — Measurement Considerations

Illustrative metrics include capture completeness, override auditability, artifact verification success, and reconstruction latency.

---

## Appendix B — Terminology

The following terminology is defined for use within DDGI. Where applicable, terms align with existing vocabulary standards including ISO 15489-1:2016 [3] and the W3C Data Privacy Vocabulary (DPV) [19].

| Term | Definition | Related Standard |
|------|-----------|------------------|
| **Decision artifact** | A structured lifecycle record capturing the context, deliberation, resolution, and provenance of an institutional decision | ISO 15489-1 "record" |
| **Procedural integrity** | The property that a decision followed its defined governance pathway, verifiable through preserved artifacts | ISO 37000 "accountability" |
| **Provenance** | The verifiable lineage of decision formation, including inputs, participants, and temporal sequence | W3C PROV-DM [16] |
| **Decision lifecycle** | The five-phase progression from initiation through reconstruction (see Section 4) | — |
| **Governance primitive** | A measurable institutional control that produces decision evidence artifacts | — |
| **Evidence survivability** | The property that decision artifacts remain intact and verifiable across organizational change | ISO 22301 "continuity" |
| **Drift detection** | The ongoing verification that decision context and compliance posture have not materially changed | ISO 31000 "monitoring and review" |

---

## Appendix C — Decision Governance Maturity Index (DDGMI)

Level 1 — Informal capture
Level 2 — Structured recording
Level 3 — Procedural traceability
Level 4 — Integrity assurance
Level 5 — Governance optimization

---

## Conclusion

Institutional accountability requires demonstrable procedural lineage. DDGI enables organizations to preserve decision provenance and withstand scrutiny while maintaining implementation flexibility.

The framework addresses a specific gap in the current standards landscape: while ISO 31000 governs risk management, ISO 15489 governs records, and ISO/IEC 42001 governs AI systems, no existing standard defines a structured evidence infrastructure for the decision act itself. DDGI fills this gap with a minimal, extensible primitive set that is vendor-neutral, implementation-agnostic, and compatible with existing governance architectures.

---

# References

[1] European Parliament and Council of the European Union. "Regulation (EU) 2024/1689 laying down harmonised rules on artificial intelligence (AI Act)." *Official Journal of the European Union*, 2024.

[2] National Institute of Standards and Technology. "Artificial Intelligence Risk Management Framework (AI RMF 1.0)." NIST AI 100-1, January 2023.

[3] International Organization for Standardization. "ISO 15489-1:2016 — Information and documentation — Records management — Part 1: Concepts and principles." Geneva: ISO, 2016.

[4] International Organization for Standardization. "ISO 31000:2018 — Risk management — Guidelines." Geneva: ISO, 2018.

[5] International Organization for Standardization. "ISO/IEC 27001:2022 — Information security, cybersecurity and privacy protection — Information security management systems — Requirements." Geneva: ISO, 2022.

[6] Mittelstadt, B. D., Allo, P., Taddeo, M., Wachter, S., & Floridi, L. "The ethics of algorithms: Mapping the debate." *Big Data & Society*, 3(2), 2016.

[7] Kahneman, D., Sibony, O., & Sunstein, C. R. *Noise: A Flaw in Human Judgment.* Little, Brown Spark, 2021.

[8] International Organization for Standardization. "ISO/IEC 38507:2022 — Information technology — Governance of IT — Governance implications of the use of artificial intelligence by organizations." Geneva: ISO, 2022.

[9] International Organization for Standardization. "ISO/IEC 23894:2023 — Information technology — Artificial intelligence — Guidance on risk management." Geneva: ISO, 2023.

[10] International Organization for Standardization. "ISO 37000:2021 — Governance of organizations — Guidance." Geneva: ISO, 2021.

[11] Organisation for Economic Co-operation and Development. "Recommendation of the Council on Artificial Intelligence." OECD/LEGAL/0449, 2019.

[12] Raji, I. D., Smart, A., White, R. N., Mitchell, M., Gebru, T., Hutchinson, B., Smith-Loud, J., Theron, D., & Barnes, P. "Closing the AI accountability gap: Defining an end-to-end framework for internal algorithmic auditing." *Proceedings of the 2020 Conference on Fairness, Accountability, and Transparency (FAT*)*, 2020.

[13] International Organization for Standardization. "ISO 22301:2019 — Security and resilience — Business continuity management systems — Requirements." Geneva: ISO, 2019.

[14] Argote, L. & Miron-Spektor, E. "Organizational learning: From experience to knowledge." *Organization Science*, 22(5), 1123–1137, 2011.

[15] International Organization for Standardization. "ISO/IEC 42001:2023 — Information technology — Artificial intelligence — Management system." Geneva: ISO, 2023.

[16] World Wide Web Consortium. "PROV-DM: The PROV Data Model." W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-dm/

[17] Metaxa, D., Park, J. S., Landay, J. A., & Hancock, J. "Auditing algorithms: Understanding algorithmic systems from the outside in." *Foundations and Trends in Human-Computer Interaction*, 14(4), 272–344, 2021.

[18] International Organization for Standardization. "ISO/IEC TR 24028:2020 — Information technology — Artificial intelligence — Overview of trustworthiness in artificial intelligence." Geneva: ISO, 2020.

[19] W3C Data Privacy Vocabularies and Controls Community Group. "Data Privacy Vocabulary (DPV)." W3C Community Group Report, 2024. https://w3c.github.io/dpv/dpv/

[20] International Organization for Standardization. "ISO/IEC 42005:2025 — Information technology — Artificial intelligence — AI system impact assessment." Geneva: ISO, 2025.

---

End of Document
