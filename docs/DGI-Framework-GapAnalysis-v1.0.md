# DGI Framework — Gap Analysis v1.0

## Standards Gap Analysis for Decision Governance Infrastructure

**Document ID:** DGI-GA-2026-001  
**Version:** 1.0  
**Date:** February 2026  
**Status:** Draft for Review  
**Target Committee:** ISO/IEC JTC 1/SC 42 — Artificial Intelligence

---

## 1. Purpose

This document identifies specific gaps in existing international standards that necessitate a new specification for **decision evidence artifacts** in AI-assisted decision-making. It demonstrates that no existing standard defines the artifact formats, integrity mechanisms, or scoring methodology required to produce verifiable evidence trails for consequential decisions.

---

## 2. Standards Examined

| Standard | Full Title | Year | Issuing Body |
|----------|-----------|:----:|:------------:|
| ISO/IEC 42001 | Information technology — AI — Management system | 2023 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC 38507 | Information technology — Governance of IT — Governance implications of the use of AI | 2022 | ISO/IEC JTC 1/SC 40 |
| ISO/IEC 23894 | Information technology — AI — Guidance on risk management | 2023 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC 22989 | Information technology — AI — AI concepts and terminology | 2022 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC 23053 | Framework for AI systems using ML | 2022 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC TR 24028 | Information technology — AI — Overview of trustworthiness | 2020 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC TR 24368 | Information technology — AI — Overview of ethical and societal concerns | 2022 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC 5338 | Information technology — AI — AI system life cycle processes | 2023 | ISO/IEC JTC 1/SC 42 |
| ISO/IEC TS 6254 | Information technology — AI — Objectives and approaches for explainability | WD | ISO/IEC JTC 1/SC 42 |
| ISO/IEC 42005 | Information technology — AI — AI system impact assessment | CD | ISO/IEC JTC 1/SC 42 |
| ISO 31000 | Risk management — Guidelines | 2018 | ISO/TC 262 |
| ISO/IEC 27001 | Information security management systems | 2022 | ISO/IEC JTC 1/SC 27 |
| NIST AI RMF 1.0 | AI Risk Management Framework | 2023 | US NIST |
| IEEE 7000 | Model process for addressing ethical concerns during system design | 2021 | IEEE |

---

## 3. The Identified Gap

### 3.1 Problem Statement

When an AI-assisted decision is challenged under adversarial scrutiny — litigation, regulatory investigation, or public inquiry — the organization must produce evidence answering three questions:

1. **Temporal:** When did the organization acquire relevant knowledge? *(Discovery-time proof)*
2. **Procedural:** What alternatives were considered, and what reasoning was applied? *(Deliberation capture)*
3. **Accountability:** Who made the final decision, and were AI recommendations overridden? *(Override accountability)*

**No existing international standard specifies the artifact formats, integrity mechanisms, or lifecycle management required to answer these questions.**

### 3.2 Why This Matters Now

| Driver | Regulation | Gap |
|--------|-----------|-----|
| EU AI Act (2024) | Art. 12 requires "automatic recording of events" for high-risk AI | Does not specify artifact format, integrity, or retention requirements |
| DORA (2025) | Art. 17 requires "comprehensive ICT-related incident registers" | Does not specify decision evidence standards |
| US EO 14110 (2023) | Requires AI safety testing and red-teaming | No evidence artifact standard for test results |
| BCBS 239 (2013) | Requires "accurate, reliable, timely" risk data | No standard for AI decision data artifacts |

---

## 4. Per-Standard Gap Analysis

### 4.1 ISO/IEC 42001:2023 — AI Management System

| 42001 Clause | Requirement | Evidence Gap |
|:------------:|------------|-------------|
| 5.2 | AI policy and leadership commitment | No artifact format for evidencing policy compliance |
| 6.1.2 | AI risk assessment | No integrity mechanism for risk assessment records |
| 6.1.4 | AI system impact assessment | No specification for preserving impact assessment results |
| 8.2 | AI risk treatment | No non-repudiation mechanism for treatment decisions |
| 8.4 | AI system operation and monitoring | No cryptographic timestamping or tamper evidence |
| 9.1 | Monitoring, measurement, analysis | No format for preserving measurement results |
| 10.1 | Continual improvement | No evidence artifact for improvement decisions |

**Conclusion:** ISO/IEC 42001 defines *what organizations must do* but not *how to produce verifiable evidence that they did it*. DGI fills this gap.

### 4.2 ISO/IEC 38507:2022 — AI Governance

| Gap Area | Detail |
|----------|--------|
| Artifact specification | No evidence format for board-level AI governance decisions |
| Temporal proof | No mechanism for proving when governance actions occurred |
| Dissent preservation | No requirement for preserving dissenting board views |
| Scoring/measurement | No quantitative governance metric |

**Conclusion:** ISO/IEC 38507 defines governance *principles* (evaluate, direct, monitor). DGI defines governance *evidence*.

### 4.3 ISO/IEC 23894:2023 — AI Risk Management

| Gap Area | Detail |
|----------|--------|
| Artifact preservation | Risk assessments are performed but no artifact format is specified |
| Temporal integrity | No requirement for timestamping when risks were identified |
| Decision linkage | No mechanism linking risk assessments to the decisions they inform |
| Drift detection | No specification for continuous compliance monitoring |

**Conclusion:** ISO/IEC 23894 defines *how to assess risk*. DGI defines *how to prove risk was assessed*.

### 4.4 NIST AI Risk Management Framework 1.0

| Gap Area | Detail |
|----------|--------|
| Normative status | Guidance only — no normative artifact requirements |
| Artifact model | "Govern" function undefined at artifact level |
| Measurement | No quantitative scoring methodology |
| Implementation | No concrete artifact specifications or schemas |

**Conclusion:** NIST AI RMF defines governance *functions*. DGI provides *implementable artifacts* for those functions.

### 4.5 IEEE 7000-2021 — Ethical Design

| Gap Area | Detail |
|----------|--------|
| Lifecycle phase | Design-time only — no runtime evidence preservation |
| Adversarial scrutiny | Not designed for litigation or regulatory investigation |
| Cryptographic integrity | No hash-chain, timestamp, or signature requirements |

**Conclusion:** IEEE 7000 addresses *design ethics*. DGI addresses *runtime evidence*.

---

## 5. Capability Gap Matrix

| Capability | 42001 | 38507 | 23894 | NIST | 7000 | OECD | **DGI** |
|-----------|:-----:|:-----:|:-----:|:----:|:----:|:----:|:-------:|
| Management system requirements | ✅ | | | | | | |
| Board governance principles | | ✅ | | | | ✅ | |
| Risk assessment methodology | | | ✅ | ✅ | | | |
| Ethical design process | | | | | ✅ | ✅ | |
| **Decision artifact specification** | | | | | | | **✅** |
| **Cryptographic timestamping** | | | | | | | **✅** |
| **Deliberation evidence capture** | | | | | | | **✅** |
| **Override detection & accountability** | | | | | | | **✅** |
| **Cognitive bias detection** | | | | | | | **✅** |
| **Continuous drift detection** | | | | | | | **✅** |
| **Post-quantum evidence integrity** | | | | | | | **✅** |
| **Cross-jurisdiction conflict resolution** | | | | | | | **✅** |
| **Quantitative governance scoring** | | | | | | | **✅** |
| **Court-admissible evidence export** | | | | | | | **✅** |

**Finding:** 10 capabilities (bolded) are addressed exclusively by DGI. Zero overlap with existing standards.

---

## 6. SC 42 Work Programme Review

Active work items in ISO/IEC JTC 1/SC 42 as of February 2026:

| Work Item | Overlap with DGI? | Rationale |
|-----------|:-----------------:|-----------|
| ISO/IEC 42001 (AIMS) | ❌ | Management system — not evidence artifacts |
| ISO/IEC 42005 (Impact Assessment) | ❌ | Assessment methodology — not evidence preservation |
| ISO/IEC 42006 (AIMS Auditor) | ❌ | Auditor competence — not evidence format |
| ISO/IEC TS 6254 (Explainability) | Marginal | Explainability concepts overlap with P2, but no artifact specification |
| ISO/IEC 12792 (Transparency) | ❌ | Transparency taxonomy — not evidence artifacts |
| ISO/IEC 42105 (Risk Management Guidance) | ❌ | Risk guidance — not evidence specification |

**Conclusion:** No active SC 42 work item addresses decision evidence artifact specification.

---

## 7. Recommendation

The gap analysis demonstrates that:

1. **The gap is real:** No existing standard specifies decision evidence artifacts
2. **The gap is urgent:** EU AI Act, DORA, and other regulations require evidence that no standard defines
3. **The gap is structural:** It exists at a layer below management systems and above security controls
4. **The gap is not addressed by any work in progress** within SC 42

**Recommended action:** Submit DGI as a New Work Item Proposal (NP) to ISO/IEC JTC 1/SC 42, positioned as a complementary artifact specification to ISO/IEC 42001.

---

*DGI Framework Gap Analysis v1.0*
