# DCII Compliance Mapping

**Version 2.1 | February 2026**

This document maps DCII primitives to specific regulatory requirements across major governance frameworks.

---

## Primitive-to-Regulation Matrix

| Regulation | P1 | P2 | P3 | P4 | P5 | P6 | P7 | P8 | P9 |
|------------|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| **EU AI Act** | ■ | | | ■ | ■ | ■ | | ■ | |
| **DORA** | ■ | | | | ■ | | | | ■ |
| **NIST AI RMF** | ■ | ■ | ■ | ■ | ■ | ■ | ■ | ■ | ■ |
| **GDPR** | | | | ■ | | | | | ■ |
| **HIPAA** | | | | ■ | ■ | | | | |
| **Basel III** | ■ | ■ | ■ | | ■ | | | | ■ |
| **SOC2** | ■ | | ■ | ■ | ■ | | | | |
| **CMMC** | | | ■ | ■ | ■ | | ■ | | |
| **FedRAMP** | ■ | | ■ | ■ | ■ | | ■ | | |
| **ISO 27001** | ■ | | | ■ | ■ | | | | |
| **PCI DSS** | ■ | | | | ■ | | | | |

■ = Direct coverage

---

## EU AI Act

| Article | Requirement | Primitive(s) | Implementation |
|---------|-------------|:------------:|----------------|
| Art. 12 | Record-keeping for high-risk AI | P1, P4 | Immutable hash-chained logs, 7-year retention |
| Art. 13 | Transparency and information | P2, P6 | Regulator's Receipt™ with full lineage |
| Art. 14 | Human oversight | P3 | Override tracking with mandatory rationale and approval workflows |
| Art. 52 | Transparency for synthetic content | P8 | C2PA content credentials on all AI-generated media |
| Art. 61 | Post-market monitoring | P5, Similarity | Outcome tracking, drift detection, pattern analysis |

---

## DORA (Digital Operational Resilience Act)

| Article | Requirement | Primitive(s) | Implementation |
|---------|-------------|:------------:|----------------|
| Art. 5 | ICT risk management | All | Decision risk treated as operational risk |
| Art. 11 | ICT-related incident testing | Similarity | Decision pattern testing and failure mode analysis |
| Art. 17 | Reporting of major incidents | P1 | Tamper-proof logs with RFC 3161 timestamps |
| Art. 28 | Third-party ICT risk | P9 | Cross-jurisdiction vendor risk tracking |

---

## NIST AI Risk Management Framework

| Function | Primitive(s) | Implementation |
|----------|:------------:|----------------|
| **Govern** | All | Comprehensive governance infrastructure across all 9 primitives |
| **Map** | P5, P9 | Risk mapping via drift detection and jurisdiction analysis |
| **Measure** | IISS™ | Quantitative resilience measurement (0–1000 score) |
| **Manage** | P6, P2 | Risk mitigation via bias detection and deliberation capture |

---

## GDPR

| Article | Requirement | Primitive(s) | Implementation |
|---------|-------------|:------------:|----------------|
| Art. 22 | Automated decision-making safeguards | P2, P3 | Human override capability with rationale capture |
| Art. 32 | Security of processing | P4 | Personnel-independent knowledge preservation |
| Art. 35 | Data protection impact assessment | P5, P6 | Continuous monitoring and bias mitigation |
| Art. 44–50 | International transfers | P9 | Cross-jurisdiction compliance with conflict resolution |

---

## HIPAA

| Requirement | Primitive(s) | Implementation |
|-------------|:------------:|----------------|
| §164.312 | Technical safeguards | P4 | Access controls and audit logging for decision records |
| §164.312(b) | Audit controls | P1, P5 | Timestamped audit trail with drift monitoring |
| §164.312(c) | Integrity | P7 | Post-quantum signatures on clinical decision records |

---

## Basel III

| Requirement | Primitive(s) | Implementation |
|-------------|:------------:|----------------|
| Operational risk | P1, P2, P3 | Decision evidence for trading and lending decisions |
| Model risk (SR 11-7) | P5, P6 | Drift detection on model outputs, bias monitoring |
| Data governance | P4, P9 | Knowledge preservation across jurisdictions |

---

## SOC2 Trust Services Criteria

| Criterion | Primitive(s) | Implementation |
|-----------|:------------:|----------------|
| CC6.1 | P3, P1 | Access controls with timestamped override tracking |
| CC7.2 | P5 | Continuous compliance monitoring with anomaly detection |
| CC8.1 | P4 | Change management with deterministic replay |
| A1.2 | P1 | Recovery point objectives with timestamp verification |

---

## Additional Frameworks

### FDA PCCP (Predetermined Change Control Plan)
- **P2** tracks model versions and training data
- **P3 + P1** prove when AI model changes occurred
- **P8** authenticates medical training images

### eIDAS (EU 910/2014)
- **P1** provides qualified timestamps (Article 41)
- **P3** provides qualified electronic signatures
- **P7** ensures long-term signature validity

### ISO/IEC 42001 (AI Management System)
- DCII adds the cryptographic evidence layer that ISO 42001 lacks
- Maps to clauses 6.1 (risk), 8.2 (AI impact), 9.1 (monitoring)

---

## IISS™ Regulatory Readiness Assessments

The IISS includes specific readiness assessments for:

| Framework | Score Range | Ready Flag | What It Measures |
|-----------|:----------:|:----------:|-----------------|
| EU AI Act | 0–100 | ✅/❌ | Articles 12–14, 52, 61 coverage |
| ABA Opinion 512 | 0–100 | ✅/❌ | Legal AI governance readiness |
| Basel III | 0–100 | ✅/❌ | Operational risk evidence coverage |
| GDPR | 0–100 | ✅/❌ | Data protection decision governance |
| HIPAA | 0–100 | ✅/❌ | Protected health information decisions |
| SOC2 | 0–100 | ✅/❌ | Trust services criteria alignment |
| CMMC | 0–100 | ✅/❌ | Cybersecurity maturity for defense |

Each assessment produces a score, `ready` boolean, and specific gap list.

---

*DCII Framework v2.1 — Datacendia, LLC*
