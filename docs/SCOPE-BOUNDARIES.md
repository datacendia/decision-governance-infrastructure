# DGI Scope Boundaries

**Document Type:** ISO New Work Item Proposal — Scope Definition  
**Version:** 1.0 | February 2026  
**Purpose:** Unambiguously define where DGI begins and ends relative to adjacent standards

---

## 1. Normative Scope Statement

**DGI is a decision evidence infrastructure specification.**

DGI defines the artifacts, integrity mechanisms, and scoring methodology required to generate, preserve, verify, and export cryptographic evidence trails for AI-assisted decisions.

**DGI is NOT:**
- A risk management system (→ ISO/IEC 23894, NIST AI RMF)
- An AI management system (→ ISO/IEC 42001)
- A governance framework (→ ISO/IEC 38507)
- An ethical design process (→ IEEE 7000)
- A model explainability framework (→ ISO/IEC TS 6254)
- A data protection regulation (→ GDPR, PIPL, etc.)
- A security management system (→ ISO/IEC 27001)

---

## 2. Boundary Diagram

```
┌──────────────────────────────────────────────────────────────────────┐
│                        ORGANIZATIONAL GOVERNANCE                     │
│  ┌────────────────────┐  ┌────────────────────┐  ┌───────────────┐  │
│  │  ISO/IEC 38507     │  │  OECD Principles   │  │  Board Policy │  │
│  │  (Board governance)│  │  (Values & norms)  │  │  & Strategy   │  │
│  └────────┬───────────┘  └────────┬───────────┘  └───────┬───────┘  │
│           │                       │                       │          │
│  ┌────────▼───────────────────────▼───────────────────────▼───────┐  │
│  │                    ISO/IEC 42001 — AIMS                        │  │
│  │     Plan → Do → Check → Act (Management System)               │  │
│  │     • Organizational requirements                              │  │
│  │     • Risk treatment processes                                 │  │
│  │     • Roles, responsibilities, competence                      │  │
│  │     • Internal audit, management review                        │  │
│  └────────┬──────────────────────────────────────────────┬───────┘  │
│           │                                              │          │
│  ┌────────▼───────────┐                        ┌─────────▼───────┐  │
│  │  ISO/IEC 23894     │                        │  IEEE 7000      │  │
│  │  (Risk management) │                        │  (Ethical design)│  │
│  │  • Risk ID         │                        │  • Values       │  │
│  │  • Risk analysis   │                        │  • Trade-offs   │  │
│  │  • Risk evaluation │                        │  • Stakeholders │  │
│  └────────┬───────────┘                        └─────────┬───────┘  │
│           │                                              │          │
│  ═════════╪══════════════════════════════════════════════╪════════  │
│           │         DGI BOUNDARY — EVIDENCE LAYER        │          │
│  ═════════╪══════════════════════════════════════════════╪════════  │
│           │                                              │          │
│  ┌────────▼──────────────────────────────────────────────▼───────┐  │
│  │              DGI — Decision Evidence Infrastructure            │  │
│  │                                                                │  │
│  │  INPUTS (from above):          OUTPUTS (evidence artifacts):  │  │
│  │  • Decisions to record         • Decision Packets (signed)    │  │
│  │  • Risk assessments to         • Timestamp Tokens (RFC 3161)  │  │
│  │    preserve                    • Bias Analysis Reports        │  │
│  │  • Deliberations to capture    • Override Records             │  │
│  │  • Overrides to detect         • Regulator's Receipt™        │  │
│  │                                • IISS Score (0–1000)          │  │
│  │                                                                │  │
│  │  9 Primitives:                                                │  │
│  │  P1 Discovery-Time │ P2 Deliberation │ P3 Override            │  │
│  │  P4 Memory         │ P5 Drift        │ P6 Bias                │  │
│  │  P7 Quantum        │ P8 Media        │ P9 Jurisdiction        │  │
│  └────────────────────────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 3. Precise Boundary Definitions

### 3.1 Where does DGI stop and ISO/IEC 42001 begin?

| Responsibility | ISO/IEC 42001 | DGI |
|---------------|:-------------:|:---:|
| Define AI policy | ✅ | |
| Establish roles and competencies | ✅ | |
| Conduct risk assessment | ✅ | |
| Define risk treatment plans | ✅ | |
| **Record evidence of decisions** | | **✅** |
| **Timestamp and sign records** | | **✅** |
| **Detect overrides** | | **✅** |
| **Score governance posture** | | **✅** |
| Perform internal audits | ✅ | |
| **Provide audit evidence artifacts** | | **✅** |
| Conduct management reviews | ✅ | |
| **Preserve review deliberations** | | **✅** |

**The boundary is clear:** 42001 defines *what organizations must do*. DGI defines *how to produce evidence that they did it*.

### 3.2 Where does DGI stop and ISO/IEC 23894 begin?

| Responsibility | ISO/IEC 23894 | DGI |
|---------------|:-------------:|:---:|
| Identify AI risks | ✅ | |
| Analyze risk likelihood and impact | ✅ | |
| Evaluate risk acceptability | ✅ | |
| Select risk treatments | ✅ | |
| **Preserve risk decision evidence** | | **✅** |
| **Timestamp when risks were identified** | | **✅** |
| **Record who accepted/rejected risks** | | **✅** |
| **Detect drift from risk baselines** | | **✅** |

**The boundary is clear:** 23894 defines *how to assess risk*. DGI defines *how to prove risk was assessed*.

### 3.3 Where does DGI stop and ISO/IEC 38507 begin?

| Responsibility | ISO/IEC 38507 | DGI |
|---------------|:-------------:|:---:|
| Evaluate AI opportunities and risks | ✅ | |
| Direct AI strategy and policy | ✅ | |
| Monitor AI outcomes | ✅ | |
| **Produce evidence of governance actions** | | **✅** |
| **Preserve board deliberations** | | **✅** |
| **Score governance effectiveness** | | **✅** |

**The boundary is clear:** 38507 defines *governance responsibilities*. DGI defines *governance evidence*.

### 3.4 Where does DGI stop and NIST AI RMF begin?

| Responsibility | NIST AI RMF | DGI |
|---------------|:-----------:|:---:|
| Govern: establish AI governance culture | ✅ | |
| Map: identify and categorize AI risks | ✅ | |
| Measure: assess AI system trustworthiness | ✅ | |
| Manage: treat and monitor AI risks | ✅ | |
| **Produce governance evidence artifacts** | | **✅** |
| **Quantify governance with IISS score** | | **✅** |

**The boundary is clear:** NIST defines *governance functions*. DGI implements *governance evidence* within those functions.

### 3.5 Where does DGI stop and ISO/IEC 27001 begin?

| Responsibility | ISO/IEC 27001 | DGI |
|---------------|:-------------:|:---:|
| Information security management | ✅ | |
| Access controls and security policies | ✅ | |
| Incident management | ✅ | |
| **Post-quantum cryptographic integrity for decisions** | | **✅** |
| **Decision-specific audit trails** | | **✅** |

**The boundary is clear:** 27001 secures *information assets*. DGI secures *decision evidence*.

---

## 4. What DGI Does NOT Address

To further clarify scope, DGI explicitly does **not** address:

| Topic | Why Not | Covered By |
|-------|---------|-----------|
| AI model training and validation | Out of scope — DGI addresses decisions, not models | ISO/IEC 23053, 5338 |
| AI system testing and evaluation | Out of scope — DGI addresses evidence, not testing | ISO/IEC 42001 Clause 8.4 |
| Data quality and data management | Out of scope — DGI assumes data exists | ISO 8000, ISO/IEC 5259 |
| AI ethics and values alignment | Out of scope — DGI preserves evidence, not values | IEEE 7000, OECD Principles |
| Cybersecurity controls | Out of scope — DGI uses crypto but is not a security standard | ISO/IEC 27001 |
| Organizational change management | Out of scope — DGI is a technical specification | ISO/IEC 42001 Clause 7 |
| AI system performance metrics | Out of scope — DGI measures governance, not AI performance | ISO/IEC 42001 Clause 9 |
| Privacy impact assessment | Out of scope — DGI preserves decisions, not personal data | ISO/IEC 27701, GDPR Art. 35 |

---

## 5. Integration Pattern

The recommended integration pattern positions DGI as the evidence layer beneath the management system:

```
Organization implements ISO/IEC 42001 (AIMS)
  ├── Uses ISO/IEC 23894 for risk management
  ├── Uses IEEE 7000 for ethical design
  ├── Uses ISO/IEC 38507 for board governance
  │
  └── Uses DGI for decision evidence
        ├── Every risk decision → Decision Packet + Timestamp
        ├── Every governance action → Deliberation Record
        ├── Every override → Override Record (non-suppressible)
        ├── Every audit cycle → Regulator's Receipt™
        └── Continuous → IISS Score tracking
```

**DGI enriches adjacent standards — it does not compete with or replace them.**

---

## 6. Formal Scope Statement (for ISO NP submission)

> **Scope:** This document specifies the requirements for decision evidence artifacts in AI-assisted decision-making. It defines 9 measurable primitives for generating, preserving, verifying, and exporting cryptographic evidence trails that enable organizations to demonstrate decision governance under adversarial scrutiny.
>
> This document applies to any organization that uses AI systems to assist, inform, or automate consequential decisions and needs to produce evidence of decision governance for regulatory, legal, audit, or insurance purposes.
>
> This document does not specify requirements for AI management systems (covered by ISO/IEC 42001), AI risk management (covered by ISO/IEC 23894), AI governance principles (covered by ISO/IEC 38507), or information security management (covered by ISO/IEC 27001). It is designed to be used in conjunction with these standards as a complementary evidence layer.

---

*Decision Governance Infrastructure — Datacendia, LLC*
