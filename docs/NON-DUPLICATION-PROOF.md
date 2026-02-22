# Non-Duplication Proof: DGI vs. Existing Standards

**Document Type:** ISO New Work Item Proposal — Non-Duplication Analysis  
**Version:** 1.0 | February 2026  
**Purpose:** Demonstrate that DGI does not duplicate existing international standards

---

## 1. Summary

This document provides a systematic comparison of DGI against all relevant existing standards, demonstrating that **no existing standard specifies decision evidence artifacts** — the core contribution of DGI.

---

## 2. Primary Gap Analysis Table

| Existing Standard | Scope | DGI Gap (What It Lacks) | DGI Contribution | Relationship |
|-------------------|-------|------------------------|-----------------|-------------|
| **ISO/IEC 42001:2023** | AI management system (AIMS) | Does not define evidence artifact formats, cryptographic integrity, or temporal proof for decisions | DGI specifies 9 evidence primitives with defined artifacts, scoring, and export formats | **Complementary** — DGI provides the evidence layer 42001 implementations need |
| **ISO/IEC 38507:2022** | Board governance of AI | High-level principles only (evaluate, direct, monitor); no implementation specification | DGI operationalizes governance principles into verifiable evidence artifacts | **Complementary** — DGI implements 38507's governance intent |
| **ISO/IEC 23894:2023** | AI risk management | Risk methodology without artifact preservation; no normative evidence requirements | DGI preserves risk decisions as tamper-evident, timestamped artifacts | **Complementary** — DGI preserves 23894 risk outputs |
| **NIST AI RMF 1.0** | AI risk management (US) | Guidance only — no normative artifact model; "Govern" function undefined at artifact level | DGI implements the "Govern" function with concrete primitives and scoring (IISS) | **Complementary** — DGI operationalizes NIST "Govern" |
| **IEEE 7000-2021** | Ethical design process | Design-time ethics only; no runtime evidence; no adversarial scrutiny capability | DGI operates at runtime — preserving evidence as decisions occur | **Complementary** — DGI extends 7000 to runtime |
| **OECD AI Principles** | Policy norms | High-level values (transparency, accountability, fairness); no implementation specification | DGI operationalizes principles into measurable, verifiable primitives | **Complementary** — DGI implements OECD intent |
| **ISO/IEC 22989:2022** | AI terminology | Vocabulary only — no requirements or specifications | DGI uses 22989 terminology; introduces 9 new terms (primitives) consistent with vocabulary | **Uses** — DGI extends 22989 vocabulary |
| **ISO/IEC 23053:2022** | ML system framework | ML pipeline lifecycle; no decision evidence | DGI addresses decision lifecycle, not model lifecycle | **Non-overlapping** — different lifecycle scope |
| **ISO/IEC 5338:2023** | AI system lifecycle | System lifecycle processes; no decision artifact specification | DGI addresses decision artifacts within the operational phase of 5338 | **Complementary** — DGI enriches 5338 operational phase |
| **ISO/IEC TR 24028:2020** | Trustworthiness overview | Conceptual trustworthiness taxonomy; no implementation specification | DGI provides implementable trustworthiness evidence | **Complementary** — DGI implements trustworthiness |
| **ISO/IEC TR 24368:2022** | Ethical/societal concerns | Overview of concerns; no evidence or artifact model | DGI addresses concerns with concrete evidence mechanisms | **Complementary** — DGI operationalizes concerns |
| **ISO 31000:2018** | General risk management | Generic risk framework; not AI-specific; no evidence artifacts | DGI is AI-decision-specific with cryptographic evidence | **Non-overlapping** — different domain scope |
| **ISO/IEC 27001:2022** | Information security | Security management system; no decision evidence | DGI's P7 (quantum-resistant integrity) extends security to decision evidence | **Complementary** — DGI extends security to decisions |
| **ISO 19011:2018** | Management system auditing | Audit methodology; no decision artifact format for AI | DGI produces artifacts that make 19011 audits more effective | **Complementary** — DGI improves audit evidence |

---

## 3. Capability Matrix

This matrix shows which capabilities are covered by existing standards vs. DGI:

| Capability | 42001 | 38507 | 23894 | NIST | 7000 | OECD | **DGI** |
|-----------|:-----:|:-----:|:-----:|:----:|:----:|:----:|:-------:|
| Management system requirements | ✅ | | | | | | |
| Board governance principles | | ✅ | | | | ✅ | |
| Risk assessment methodology | | | ✅ | ✅ | | | |
| Ethical design process | | | | | ✅ | ✅ | |
| **Cryptographic timestamping** | | | | | | | **✅** |
| **Decision artifact specification** | | | | | | | **✅** |
| **Deliberation evidence capture** | | | | | | | **✅** |
| **Override detection & accountability** | | | | | | | **✅** |
| **Institutional knowledge preservation** | | | | | | | **✅** |
| **Continuous compliance drift detection** | | | | | | | **✅** |
| **Cognitive bias detection & mitigation** | | | | | | | **✅** |
| **Post-quantum evidence integrity** | | | | | | | **✅** |
| **Synthetic media authentication** | | | | | | | **✅** |
| **Cross-jurisdiction conflict resolution** | | | | | | | **✅** |
| **Quantitative governance scoring (IISS)** | | | | | | | **✅** |
| **Court-admissible evidence export** | | | | | | | **✅** |

**Result:** The bottom 11 capabilities (bolded) are unique to DGI. No existing standard addresses any of them.

---

## 4. Artifact Type Analysis

DGI defines specific artifact types that no existing standard specifies:

| DGI Artifact | Format | Integrity | Existing Standard Coverage |
|-------------|--------|-----------|--------------------------|
| **Decision Packet** | JSON (schema-defined) | SHA-256 + PQ signature | ❌ None |
| **Regulator's Receipt™** | PDF/JSON/XML | Signed + timestamped | ❌ None |
| **Timestamp Token** | RFC 3161 + blockchain anchor | Multi-layer verification | ❌ None (RFC 3161 exists but not applied to AI decisions) |
| **Bias Analysis Report** | JSON (schema-defined) | SHA-256 integrity hash | ❌ None |
| **Override Record** | JSON (immutable) | Non-suppressible, signed | ❌ None |
| **Dissent Preservation** | JSON (non-deletable) | Hash-locked | ❌ None |
| **Good-Faith Document** | JSON/PDF | SHA-256 + signer identity | ❌ None |
| **IISS Score** | JSON (schema-defined) | SHA-256 + signed | ❌ None |
| **Similarity Match** | JSON | Scored + ranked | ❌ None |

---

## 5. SC 42 Work Programme Analysis

As of February 2026, the following active work items in ISO/IEC JTC 1/SC 42 were reviewed for potential overlap:

| Work Item | Title | Overlap with DGI? |
|-----------|-------|:-----------------:|
| ISO/IEC 42001 | AIMS Requirements | ❌ No — management system, not evidence artifacts |
| ISO/IEC 42005 | AI System Impact Assessment | ❌ No — impact assessment methodology, not evidence preservation |
| ISO/IEC 42006 | AIMS Auditor Requirements | ❌ No — auditor competence, not evidence format |
| ISO/IEC TS 6254 | Objectives and Approaches for Explainability | Partial — explainability overlaps with P2, but 6254 does not define artifact formats |
| ISO/IEC 12792 | Transparency Taxonomy | ❌ No — taxonomy of transparency concepts, not evidence artifacts |
| ISO/IEC 42105 | Guidance for AI Risk Management | ❌ No — risk management guidance, not evidence specification |

**Finding:** No active SC 42 work item addresses decision evidence artifact specification.

---

## 6. Key Differentiators

### 6.1 DGI is an artifact specification, not a management system

| Characteristic | ISO/IEC 42001 | DGI |
|---------------|:-------------:|:---:|
| Defines organizational requirements | ✅ | ❌ |
| Defines artifact formats | ❌ | ✅ |
| Certifiable management system | ✅ | ❌ |
| Provides JSON schemas for evidence | ❌ | ✅ |
| Includes cryptographic specifications | ❌ | ✅ |
| Requires specific technology choices | ❌ | ❌ |
| Provides quantitative scoring | ❌ | ✅ |

### 6.2 DGI addresses adversarial scrutiny

No existing standard is designed for the adversarial context — litigation, regulatory investigation, public inquiry — where evidence must survive challenge. DGI's primitives are specifically designed for this use case.

### 6.3 DGI provides measurability

The IISS (0–1000 score with 5 bands and 4 certification levels) provides a **quantitative governance metric** that no existing standard offers. This enables:
- Board reporting with trend tracking
- Insurance underwriting based on governance posture
- M&A due diligence on decision risk exposure
- Regulatory self-assessment with objective scoring

---

## 7. Conclusion

DGI does not duplicate any existing international standard. It fills a clearly defined gap — **decision evidence artifact specification** — that existing standards presuppose but do not address.

The appropriate standards vehicle is either:
- **New Work Item Proposal (NP)** for a new ISO/IEC standard in SC 42
- **Technical Report (TR)** as a precursor to a full standard

**Recommended path:** Submit as NP with reference to this non-duplication analysis.

---

*Decision Governance Infrastructure — Datacendia, LLC*
