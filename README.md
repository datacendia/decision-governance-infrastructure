# DCII Framework — Decision Crisis Immunization Infrastructure

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**Version 2.1 | February 2026**

> *The open standard for auditable AI governance.*

---

## What is DCII?

The **Decision Crisis Immunization Infrastructure (DCII)** is a framework for generating cryptographically verifiable evidence trails for AI-assisted decisions. It enables organizations to survive adversarial scrutiny — litigation, regulatory investigation, or public inquiry — by proving:

1. **When** information was known (Discovery-Time Proof)
2. **What** was considered (Deliberation Capture)
3. **Who** decided and why (Override Accountability)

DCII is built on **9 measurable primitives** that collectively produce the **Institutional Immune System Score (IISS™)** — a 0–1000 metric quantifying organizational resilience to decision-related crises.

---

## The 9 Primitives

| # | Primitive | The Question It Answers |
|---|-----------|------------------------|
| P1 | **Discovery-Time Proof** | "When did you know?" |
| P2 | **Deliberation Capture** | "What did you consider?" |
| P3 | **Override Accountability** | "Who decided — and why?" |
| P4 | **Continuity Memory** | "Is knowledge preserved?" |
| P5 | **Drift Detection** | "Are you still compliant?" |
| P6 | **Cognitive Bias Mitigation** | "Did you challenge assumptions?" |
| P7 | **Quantum-Resistant Integrity** | "Is the proof future-proof?" |
| P8 | **Synthetic Media Authentication** | "Is the evidence authentic?" |
| P9 | **Cross-Jurisdiction Compliance** | "Did you comply everywhere?" |

---

## Repository Structure

```
/docs
  DCII_Framework_v2.1.md              — White paper (full framework specification)
  DGI_Framework_v2.md                 — Decision Governance Intelligence standards
  primitive-specifications.md         — Detailed specification for each primitive
  compliance-mapping.md               — Regulation-to-primitive mapping
  ISO-GAPS-IN-EXISTING-STANDARDS.md   — Gap analysis vs. ISO 42001, 38507, 23894, NIST
  GLOBAL-REGULATORY-EQUIVALENCE.md    — International applicability (23 jurisdictions)
  NON-DUPLICATION-PROOF.md            — Non-duplication analysis for ISO NP submission
  SCOPE-BOUNDARIES.md                 — Where DGI stops and adjacent standards begin
  DGI-Contributors.md                 — Expert endorsement register & contributor guide

/schemas
  decision-packet.json                — JSON Schema for Decision Packets
  regulators-receipt.json             — JSON Schema for Regulator's Receipt™
  iiss-scoring.json                   — JSON Schema for IISS scoring

/examples
  sample-decision.json                — Example decision packet
  integration-guide.md                — Step-by-step integration guide

/api
  api-spec.yaml                       — OpenAPI 3.0 specification (59 endpoints)
  webhook-spec.md                     — Webhook event documentation
```

---

## IISS™ Certification Bands

| Range | Band | Interpretation |
|:-----:|------|---------------|
| 801–1000 | **Exceptional** | Crisis-immune. >95% confidence under adversarial scrutiny. |
| 601–800 | **Resilient** | Strong coverage, minor gaps. Insurance discount eligible. |
| 401–600 | **Developing** | Core capabilities in place. Advanced primitive gaps remain. |
| 201–400 | **Vulnerable** | Partial coverage. High regulatory/litigation exposure. |
| 0–200 | **Critical** | Fundamental gaps. Cannot demonstrate basic decision governance. |

---

## Regulatory Coverage

DCII maps to the following regulatory frameworks:

- **EU AI Act** — Articles 12, 13, 14, 52, 61
- **DORA** — Articles 5, 11, 17, 28
- **NIST AI RMF** — Govern, Map, Measure, Manage functions
- **GDPR** — Articles 32, 44–50
- **HIPAA** — §164.312
- **Basel III** — Operational risk requirements
- **SOC2** — Trust services criteria
- **CMMC** — Cybersecurity maturity model
- **FedRAMP** — Federal risk authorization
- **ISO 27001** — Information security management

See [`docs/compliance-mapping.md`](docs/compliance-mapping.md) for the complete primitive-to-regulation matrix.

---

## Reference Implementation

The production reference implementation of DCII is available at [datacendia.com](https://datacendia.com).

The Datacendia platform implements all 9 primitives through:
- **6 production services** backed by **15 PostgreSQL tables**
- **59 REST API endpoints** under `/api/v1/dcii/`
- **IISS™ scoring engine** with real-time assessment
- **Regulator's Receipt™** export (PDF, JSON, XML)

---

## ISO Standardization Track

DGI is being prepared for submission to **ISO/IEC JTC 1/SC 42** (Artificial Intelligence) as a New Work Item Proposal (NP). The following documents support the submission:

- [**Gaps in Existing Standards**](docs/ISO-GAPS-IN-EXISTING-STANDARDS.md) — Why no existing ISO standard covers decision evidence artifacts
- [**Global Regulatory Equivalence**](docs/GLOBAL-REGULATORY-EQUIVALENCE.md) — Mapping to 23 jurisdictions across 7 regions (not euro/US-centric)
- [**Non-Duplication Proof**](docs/NON-DUPLICATION-PROOF.md) — Systematic comparison against 14 existing standards
- [**Scope Boundaries**](docs/SCOPE-BOUNDARIES.md) — Where DGI stops and ISO 42001/38507/23894 begin
- [**Contributors**](docs/DGI-Contributors.md) — Expert endorsement register (seeking 5+ countries)

> **DGI is not a risk management system. DGI is a decision evidence infrastructure specification.**

---

## Quick Start

1. Review the [White Paper](docs/DCII_Framework_v2.1.md) for full framework specification
2. Review [Primitive Specifications](docs/primitive-specifications.md) for implementation requirements
3. Use the [JSON Schemas](schemas/) to validate your data structures
4. Follow the [Integration Guide](examples/integration-guide.md) for step-by-step implementation
5. Reference the [API Spec](api/api-spec.yaml) for the REST API surface

---

## Citation

```bibtex
@techreport{rainey2026dcii,
  title     = {Decision Crisis Immunization Infrastructure: A Framework for Auditable AI Governance},
  author    = {Rainey, Stuart},
  year      = {2026},
  version   = {2.1},
  institution = {Datacendia, LLC},
  url       = {https://github.com/datacendia/decision-governance-infrastructure}
}
```

---

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).

You are free to share and adapt this material for any purpose, including commercial, provided you give appropriate credit.

---

**Datacendia, LLC** — *Making AI decisions provable, auditable, and defensible.*
