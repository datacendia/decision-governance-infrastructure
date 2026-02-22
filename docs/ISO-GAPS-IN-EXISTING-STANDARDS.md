# Gaps in Existing Governance Standards Requiring DGI

**Document Type:** ISO New Work Item Proposal — Gap Analysis  
**Version:** 1.0 | February 2026  
**Target Committee:** ISO/IEC JTC 1/SC 42 (Artificial Intelligence)

---

## 1. Executive Summary

Existing international standards for AI governance address management systems, risk frameworks, and ethical principles — but **none define a specification for decision evidence artifacts**: the cryptographic, temporal, and procedural records needed to prove a decision was made correctly when challenged under adversarial scrutiny.

Decision Governance Infrastructure (DGI) fills this gap by specifying **9 measurable primitives** that produce **verifiable evidence artifacts** for AI-assisted decisions. This document demonstrates that DGI does not duplicate existing standards but provides a complementary evidence layer that existing standards presuppose but do not define.

---

## 2. Standards Examined

The following international standards and frameworks were analyzed for coverage of decision evidence infrastructure:

| Standard | Full Title | Pub Date | Scope |
|----------|-----------|----------|-------|
| **ISO/IEC 42001:2023** | AI Management System | 2023-12 | AIMS requirements for organizations using AI |
| **ISO/IEC 38507:2022** | Governance Implications of the Use of AI | 2022-04 | Board-level AI governance guidance |
| **ISO/IEC 23894:2023** | AI Risk Management | 2023-02 | Risk identification, analysis, evaluation for AI |
| **ISO/IEC 22989:2022** | AI Concepts and Terminology | 2022-07 | Foundational AI vocabulary |
| **ISO/IEC 23053:2022** | Framework for AI Systems Using ML | 2022-06 | ML system lifecycle framework |
| **ISO/IEC TR 24028:2020** | Overview of Trustworthiness in AI | 2020-05 | Trustworthiness concepts for AI |
| **ISO/IEC TR 24368:2022** | Overview of Ethical and Societal Concerns | 2022-08 | Ethical considerations for AI |
| **ISO/IEC 5338:2023** | AI System Lifecycle Processes | 2023-12 | Process model for AI systems |
| **NIST AI RMF 1.0** | AI Risk Management Framework | 2023-01 | US risk management guidance |
| **IEEE 7000-2021** | Model Process for Ethical Considerations | 2021-09 | Value-based system design |
| **OECD AI Principles** | Recommendation of the Council on AI | 2019-05 | Policy-level AI principles |

---

## 3. The Decision Evidence Gap

### 3.1 The Problem

When an AI-assisted decision is challenged — in litigation, regulatory investigation, or public scrutiny — the organization must answer three evidentiary questions:

1. **Temporal:** When did the organization know what it knew? (Discovery-time proof)
2. **Procedural:** What alternatives were considered, and what reasoning was applied? (Deliberation capture)
3. **Accountability:** Who made the final decision, and did they override AI recommendations? (Override accountability)

**No existing international standard specifies how to generate, preserve, or verify the artifacts needed to answer these questions.**

### 3.2 What Existing Standards Do

| Standard | What It Provides | What It Does NOT Provide |
|----------|-----------------|-------------------------|
| **ISO/IEC 42001** | Management system requirements (plan, do, check, act) | No specification for decision evidence artifacts |
| **ISO/IEC 38507** | Board-level governance principles for AI | No implementation-level evidence requirements |
| **ISO/IEC 23894** | Risk assessment methodology | No artifact model for preserving risk decisions |
| **NIST AI RMF** | Govern/Map/Measure/Manage functions | Guidance only — no normative artifact specification |
| **IEEE 7000** | Ethical design process | No evidentiary preservation or cryptographic integrity |
| **OECD Principles** | Transparency, accountability, fairness norms | Policy-level only — no implementation specification |

### 3.3 The Consequence

Organizations implementing ISO/IEC 42001 create an AI management system — but when a regulator asks *"show me the evidence trail for Decision X from 18 months ago,"* the management system cannot produce it because:

- **42001 Clause 6.1.2** requires "AI risk assessment" but does not define the format, integrity, or retention requirements for decision records
- **42001 Clause 8.4** requires "AI system operation" documentation but does not specify cryptographic timestamping, tamper evidence, or non-repudiation
- **42001 Clause 9.1** requires "monitoring and measurement" but does not define how to preserve dissenting opinions, override rationale, or bias analysis results

**DGI provides the artifact specification that ISO/IEC 42001 implementations need but the standard does not define.**

---

## 4. Specific Gap Analysis by Standard

### 4.1 ISO/IEC 42001:2023 — AI Management System

**What 42001 requires (selected clauses):**

| Clause | Requirement | Evidence Gap |
|--------|------------|-------------|
| 5.2 | AI policy — leadership commitment | Does not specify how policy compliance is evidenced |
| 6.1.2 | AI risk assessment | Does not define artifact format or integrity requirements |
| 6.1.4 | AI system impact assessment | Does not specify how impact assessment results are preserved |
| 8.2 | AI risk treatment | Does not define how treatment decisions are recorded with non-repudiation |
| 8.4 | AI system operation and monitoring | Does not specify timestamping, tamper evidence, or retention |
| 9.1 | Monitoring, measurement, analysis | Does not define format for preserving measurement results |
| 10.1 | Continual improvement | Does not specify how improvement decisions are evidenced |

**DGI fills these gaps with:**
- P1 (Discovery-Time Proof): RFC 3161 timestamps + blockchain anchoring for temporal proof
- P2 (Deliberation Capture): Immutable multi-perspective decision records
- P3 (Override Accountability): Non-suppressible override detection and rationale capture
- P5 (Drift Detection): Continuous compliance monitoring with statistical baselines

### 4.2 ISO/IEC 38507:2022 — Governance Implications of AI

**What 38507 provides:** High-level governance principles (evaluate, direct, monitor) for boards overseeing AI.

**What it lacks:**
- No specification for how governance decisions are recorded
- No artifact model for board-level AI oversight evidence
- No mechanism for proving when governance actions were taken
- No requirement for preserving dissenting board views

**DGI fills this gap:** P2 (Deliberation Capture) + P3 (Override Accountability) provide the evidence infrastructure for board governance decisions.

### 4.3 ISO/IEC 23894:2023 / NIST AI RMF — Risk Management

**What they provide:** Structured methodologies for identifying, analyzing, and evaluating AI risks.

**What they lack:**
- Both are **guidance documents** — neither defines normative artifact specifications
- No cryptographic integrity requirements for risk assessment records
- No temporal proof requirements for when risks were identified
- No specification for preserving the full deliberation context of risk decisions

**DGI fills this gap:** The 9 primitives operationalize the "Govern" function (NIST) and "risk treatment" requirements (23894) into concrete, verifiable artifacts.

### 4.4 IEEE 7000-2021 — Ethical Considerations

**What it provides:** A model process for incorporating ethical values into system design.

**What it lacks:**
- Focused on design-time ethics, not runtime decision evidence
- No post-deployment evidence preservation
- No mechanism for adversarial scrutiny survival
- No cryptographic integrity or temporal proof

**DGI fills this gap:** DGI operates at runtime — preserving evidence of decisions as they occur, not just as they are designed.

---

## 5. Why a New Standard Is Needed

### 5.1 The standards landscape has a structural gap

```
┌─────────────────────────────────────────────────────────────┐
│                    AI Governance Stack                       │
├─────────────────────────────────────────────────────────────┤
│  OECD Principles          → Policy & Values                │
│  ISO/IEC 38507            → Board Governance                │
│  ISO/IEC 42001            → Management System               │
│  ISO/IEC 23894 / NIST RMF → Risk Management                │
│  IEEE 7000                → Ethical Design                  │
│  ─────────────────────────────────────────────────────────  │
│  ❌ [MISSING LAYER]       → Decision Evidence Artifacts     │
│  ─────────────────────────────────────────────────────────  │
│  DGI Framework            → Fills this gap                  │
└─────────────────────────────────────────────────────────────┘
```

### 5.2 The gap is not addressed by any work item in progress

As of February 2026, ISO/IEC JTC 1/SC 42 has no active work item addressing:
- Cryptographic decision evidence specifications
- Decision artifact lifecycle management
- Institutional immune system scoring
- Cross-jurisdiction decision evidence portability

### 5.3 Market demand is urgent

- **EU AI Act** (effective 2025): Article 12 requires record-keeping but does not specify artifact format
- **DORA** (effective 2025): Requires "comprehensive ICT-related incident registers" without artifact specification
- **US Executive Order 14110** (2023): Requires AI safety testing but no evidence artifact standard
- Litigation involving AI decisions is growing exponentially — courts need admissible evidence formats

---

## 6. Proposed Relationship to Existing Standards

DGI is designed as a **complementary specification** — not a replacement:

| Existing Standard | Relationship to DGI |
|-------------------|-------------------|
| ISO/IEC 42001 | DGI provides the artifact layer that 42001 implementations need |
| ISO/IEC 38507 | DGI operationalizes 38507's governance principles into evidence |
| ISO/IEC 23894 | DGI preserves risk assessment decisions as verifiable artifacts |
| NIST AI RMF | DGI implements the "Govern" function with concrete primitives |
| IEEE 7000 | DGI extends ethical design with runtime evidence preservation |

**An organization can be ISO 42001 certified AND DGI-compliant** — the two are complementary, not competing.

---

## 7. Conclusion

The international standards landscape provides comprehensive coverage for AI management, governance, risk, and ethics — but contains a structural gap in **decision evidence infrastructure**. No existing standard specifies how to generate, preserve, verify, or export the cryptographic and procedural artifacts needed to survive adversarial scrutiny of AI-assisted decisions.

DGI fills this gap with a concrete, implementable specification built on 9 measurable primitives, each with defined technical controls and scoring criteria.

**Recommendation:** Submit DGI as a New Work Item Proposal (NP) to ISO/IEC JTC 1/SC 42, positioned as a complementary specification to ISO/IEC 42001.

---

*Decision Governance Infrastructure — Datacendia, LLC*
