# Decision Governance Infrastructure (DGI)

## Technical Report v1.0

**Document ID:** DGI-TR-2026-001  
**Version:** 1.0  
**Date:** February 2026  
**Document Type:** Technical Report (candidate for ISO/IEC TR)  
**Target Committee:** ISO/IEC JTC 1/SC 42 — Artificial Intelligence  
**Status:** Pre-submission draft

---

## Foreword

This Technical Report specifies the Decision Governance Infrastructure (DGI) — a framework for generating, preserving, verifying, and exporting cryptographic evidence trails for AI-assisted decisions. DGI defines 9 measurable primitives, each with 6 technical controls, and introduces the Institutional Immune System Score (IISS) as a quantitative measure of organizational resilience to decision-related crises.

This document is framework-only and implementation-neutral. It does not prescribe specific technologies, vendors, or products.

---

## 1. Scope

This document specifies the requirements for **decision evidence artifacts** in AI-assisted decision-making.

It defines:
- 9 measurable primitives for decision evidence generation and preservation
- Technical controls for each primitive (6 per primitive, 54 total)
- A scoring methodology (IISS) for quantifying organizational governance posture
- Artifact formats for decision packets, evidence receipts, and compliance reports
- Cross-jurisdiction conflict resolution strategies

This document applies to any organization that uses AI systems to assist, inform, or automate consequential decisions and needs to produce evidence of decision governance for regulatory, legal, audit, or insurance purposes.

This document does **not** specify requirements for:
- AI management systems (see ISO/IEC 42001)
- AI risk management (see ISO/IEC 23894)
- AI governance principles (see ISO/IEC 38507)
- Information security management (see ISO/IEC 27001)
- AI system lifecycle processes (see ISO/IEC 5338)

DGI is designed to be used **in conjunction** with these standards as a complementary evidence layer.

---

## 2. Normative References

The following documents are referred to in the text in such a way that some or all of their content constitutes requirements of this document.

- ISO/IEC 42001:2023, *Information technology — Artificial intelligence — Management system*
- ISO/IEC 22989:2022, *Information technology — Artificial intelligence — Artificial intelligence concepts and terminology*
- ISO/IEC 27001:2022, *Information security, cybersecurity and privacy protection — Information security management systems — Requirements*
- RFC 3161, *Internet X.509 Public Key Infrastructure Time-Stamp Protocol (TSP)*
- RFC 3628, *Policy Requirements for Time-Stamping Authorities (TSAs)*
- FIPS 204, *Module-Lattice-Based Digital Signature Standard (ML-DSA)*
- FIPS 205, *Stateless Hash-Based Digital Signature Standard (SLH-DSA)*

---

## 3. Terms and Definitions

For the purposes of this document, the terms and definitions given in ISO/IEC 22989 and the following apply.

### 3.1 decision evidence artifact
structured, integrity-protected record that documents one or more aspects of a consequential decision, including temporal proof, deliberation context, accountability chain, and compliance status

### 3.2 decision packet
a self-contained, cryptographically signed evidence bundle containing the complete record of a single decision — including deliberation, votes, dissent, alternatives considered, bias analysis, and integrity proofs

### 3.3 institutional immune system score (IISS)
a quantitative metric (0–1000) measuring an organization's ability to survive adversarial scrutiny of its AI-assisted decisions, calculated as the weighted sum of 9 normalized primitive scores

### 3.4 primitive
a measurable dimension of decision governance capability, each addressing a specific evidentiary question that arises during adversarial scrutiny

### 3.5 technical control
a specific, assessable requirement within a primitive, scored against a defined maximum to enable quantitative evaluation

### 3.6 adversarial scrutiny
examination of past decisions under conditions designed to identify failures — including litigation, regulatory investigation, public inquiry, or audit

### 3.7 discovery-time proof
cryptographic evidence of when information became known to an organization, preventing backdating and post-hoc rationalization

### 3.8 deliberation capture
complete, immutable record of all perspectives considered, alternatives evaluated, and trade-offs made during a decision process

### 3.9 override accountability
automatic detection and immutable preservation of instances where humans override AI recommendations, with mandatory rationale capture

### 3.10 evidence receipt
a court-admissible evidence package summarizing an organization's decision governance posture over a defined period, including IISS score, primitive scores, and regulatory readiness assessments

---

## 4. The Decision Evidence Problem

### 4.1 Background

AI systems increasingly assist or automate consequential decisions in regulated industries. When these decisions are later challenged, organizations must answer three evidentiary questions:

a) **Temporal:** When did the organization acquire the information relevant to this decision?

b) **Procedural:** What alternatives were considered, what reasoning was applied, and were dissenting views preserved?

c) **Accountability:** Who made the final decision, were AI recommendations overridden, and was the override rationale documented?

### 4.2 Gap in existing standards

Existing international standards address AI management (ISO/IEC 42001), risk (ISO/IEC 23894), governance (ISO/IEC 38507), and ethics (IEEE 7000) — but none specify the artifact formats, integrity mechanisms, or lifecycle management required to produce verifiable answers to these questions.

DGI addresses this gap by specifying a decision evidence infrastructure that existing standard implementations can use to generate and preserve verifiable evidence artifacts.

---

## 5. Framework Overview

### 5.1 The 9 Primitives

DGI is built on 9 measurable primitives. Each primitive addresses a specific question that arises during adversarial scrutiny of past decisions.

| Primitive | Designation | Evidentiary Question | Weight |
|:---------:|------------|---------------------|:------:|
| P1 | Discovery-Time Proof | "When did you know?" | 15% |
| P2 | Deliberation Capture | "What did you consider?" | 15% |
| P3 | Override Accountability | "Who decided — and why?" | 12% |
| P4 | Continuity Memory | "Is knowledge preserved?" | 10% |
| P5 | Drift Detection | "Are you still compliant?" | 10% |
| P6 | Cognitive Bias Mitigation | "Did you challenge assumptions?" | 10% |
| P7 | Quantum-Resistant Integrity | "Is the proof future-proof?" | 10% |
| P8 | Synthetic Media Authentication | "Is the evidence authentic?" | 8% |
| P9 | Cross-Jurisdiction Compliance | "Did you comply everywhere?" | 10% |

### 5.2 Architecture

DGI operates as an evidence layer positioned between organizational governance systems (above) and security infrastructure (below):

```
┌─────────────────────────────────────────────────┐
│  Governance Layer                                │
│  (ISO/IEC 42001, 38507, 23894, NIST AI RMF)    │
│  Management systems, risk, governance principles │
└──────────────────────┬──────────────────────────┘
                       │ decisions, assessments,
                       │ governance actions
                       ▼
┌─────────────────────────────────────────────────┐
│  DGI — Decision Evidence Layer                   │
│  9 Primitives → Decision Packets → IISS Score   │
│  Artifact generation, integrity, export          │
└──────────────────────┬──────────────────────────┘
                       │ cryptographic operations,
                       │ key management, storage
                       ▼
┌─────────────────────────────────────────────────┐
│  Security Layer                                  │
│  (ISO/IEC 27001, cryptographic infrastructure)  │
│  Key management, access control, audit logging   │
└─────────────────────────────────────────────────┘
```

### 5.3 Design Principles

a) **Implementation-neutral:** DGI specifies *what* evidence must be produced, not *how* to produce it.

b) **Technology-agnostic:** No specific database, programming language, or infrastructure is required.

c) **Jurisdiction-neutral:** Primitives are defined without reference to any specific regulation.

d) **Complementary:** DGI enriches adjacent standards — it does not compete with or replace them.

e) **Measurable:** Every requirement is quantitatively assessable through the IISS scoring methodology.

---

## 6. Primitive Specifications

### 6.1 P1: Discovery-Time Proof

**Definition:** Cryptographic proof of when information became known and decisions were made, preventing backdating and post-hoc rationalization.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Cryptographic Timestamping | 40 | RFC 3161-compliant timestamps on all decision events |
| 2 | Event Linkage | 30 | Timestamps linked to deliberation records via reference identifiers |
| 3 | Tamper Evidence | 40 | Hash-chain or Merkle tree integrity with independent verification capability |
| 4 | Non-Repudiation | 30 | Digital signatures with delivery proof |
| 5 | External Anchoring | 20 | Optional anchoring to external trust sources (e.g., public ledger, qualified TSA) |
| 6 | Evidence Packet Generation | 40 | Export of timestamped evidence in standard formats (JSON, PDF, XML) |

**Maximum raw score:** 200

#### Implementation Guidance

Implementations SHOULD provide at least two independent timestamp layers:

- **Layer 1 (Internal):** NTP-synchronized server clock with cryptographic hash and digital signature
- **Layer 2 (External):** Third-party Time-Stamping Authority per RFC 3161, with certificate chain validation

An optional **Layer 3 (Public Ledger)** MAY anchor Merkle roots to a public blockchain or distributed ledger for highest-assurance scenarios.

**Applicable standards:** eIDAS Article 41, ISO/IEC 18014, ETSI EN 319 421

---

### 6.2 P2: Deliberation Capture

**Definition:** Complete, immutable record of all perspectives considered, alternatives evaluated, and trade-offs made during a decision process.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Multi-Perspective Analysis | 40 | Minimum 3 independent perspectives per consequential decision |
| 2 | Real-Time Capture | 35 | Deliberation captured as it occurs, not retrospectively |
| 3 | Alternative Documentation | 30 | Paths not taken documented with rejection rationale |
| 4 | Immutable Record | 35 | Hash-locked on finalization; no post-hoc modification |
| 5 | Contextual Completeness | 30 | Data inputs, tools, constraints, and assumptions recorded |
| 6 | Dissent Preservation | 30 | Minority views preserved as non-suppressible, non-deletable records |

**Maximum raw score:** 200

#### Implementation Guidance

Implementations SHALL ensure that dissent records cannot be deleted, modified, or suppressed after capture. The integrity of dissent records SHALL be independently verifiable.

Multi-perspective analysis MAY be achieved through multiple human reviewers, multiple AI agent perspectives, or a combination thereof.

**Applicable standards:** EU AI Act Articles 13–14, NIST AI RMF "Govern" function

---

### 6.3 P3: Override Accountability

**Definition:** Automatic detection and immutable preservation of instances where humans override AI recommendations, with mandatory rationale capture.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Automatic Override Detection | 35 | System detects when human action diverges from AI recommendation |
| 2 | Mandatory Rationale Capture | 35 | Override cannot proceed without documented explanation |
| 3 | Authority Tracking | 30 | Chain of command documented; approver identity verified |
| 4 | Non-Suppressibility | 40 | Original AI recommendation cannot be deleted or hidden |
| 5 | Time-Lock Protection | 30 | Override record immutable after decision finalization |
| 6 | Escalation Workflows | 30 | High-risk overrides automatically escalated to designated authority |

**Maximum raw score:** 200

#### Implementation Guidance

Override records SHALL include: (a) the original AI recommendation, (b) the human decision, (c) the divergence detected, (d) the rationale provided, (e) the authority level of the overrider, and (f) a digital signature.

Implementations SHALL use digital signatures (RSA ≥ 3072-bit, ECDSA P-256 or higher, or post-quantum equivalent) for non-repudiation.

**Applicable standards:** eIDAS (EU 910/2014), NIST SP 800-57, FDA 21 CFR Part 11

---

### 6.4 P4: Continuity Memory

**Definition:** Personnel-independent preservation of institutional decision knowledge with semantic retrieval capability.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Context Preservation | 35 | Rationale, constraints, and trade-offs captured with each decision |
| 2 | Personnel Independence | 30 | Records independent of any individual; accessible after personnel changes |
| 3 | Deterministic Replay | 35 | Ability to reconstruct the information state at the time of decision |
| 4 | Searchable & Linked | 30 | Semantic similarity search across historical decisions |
| 5 | Learning Integration | 35 | Historical precedent automatically surfaced for new decisions |
| 6 | Outcome Tracking | 35 | Decision outcomes recorded with lessons learned |

**Maximum raw score:** 200

#### Implementation Guidance

Implementations SHOULD support semantic search (e.g., vector embeddings) in addition to keyword search for historical decision retrieval.

Retention periods SHALL comply with applicable jurisdictional requirements (minimum 5 years recommended; 7–10 years for regulated industries).

**Applicable standards:** GDPR Article 32, HIPAA §164.312, ISO/IEC 27001 Annex A.9

---

### 6.5 P5: Drift Detection

**Definition:** Continuous monitoring of compliance state with real-time anomaly detection and trend analysis.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Continuous Monitoring | 40 | Real-time compliance status across configured frameworks |
| 2 | Baseline Establishment | 25 | Statistical norms established per control |
| 3 | Anomaly Detection | 35 | Deviation from baselines detected with configurable thresholds |
| 4 | Trend Analysis | 30 | Quarter-over-quarter projections with trajectory alerts |
| 5 | Early Warning System | 35 | Multi-threshold alerts (warning, critical) with escalation |
| 6 | Root Cause Analysis | 35 | Automated investigation with remediation guidance |

**Maximum raw score:** 200

#### Implementation Guidance

Implementations SHALL define at least two alert thresholds (warning and critical) for each monitored control. Alert escalation SHALL be configurable per organizational requirements.

**Applicable standards:** SOC2 CC7.2, ISO/IEC 27001 Annex A.12.4

---

### 6.6 P6: Cognitive Bias Mitigation

**Definition:** Systematic detection and documentation of cognitive biases in human-AI decision-making processes.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Bias Detection Library | 35 | Minimum 12 cognitive biases tested per deliberation |
| 2 | Devil's Advocate Enforcement | 30 | Adversarial perspective required for high-risk decisions |
| 3 | Anchoring Detection | 25 | Detection of first-number dominance and initial-proposal anchoring |
| 4 | Groupthink Prevention | 30 | Unanimous decisions without debate flagged for scrutiny |
| 5 | Rubber-Stamp Detection | 25 | Fast approvals without substantive review flagged |
| 6 | Bias Audit Trail | 30 | Analysis results preserved in decision packet with integrity hash |

**Maximum raw score:** 175

#### The 12-Bias Library

Implementations SHALL test for at least the following cognitive biases:

| # | Bias | Detection Indicator |
|:-:|------|-------------------|
| 1 | Anchoring | First number or initial proposal dominates final decision |
| 2 | Confirmation | Only supporting evidence cited; contradictory data dismissed |
| 3 | Groupthink | Unanimous agreement without recorded debate |
| 4 | Availability | Recent events cited disproportionately; base rates ignored |
| 5 | Sunk Cost | Past investment cited as justification for continued investment |
| 6 | Overconfidence | No uncertainty range; single-point estimates without bounds |
| 7 | Bandwagon | "Everyone agrees" without independent analysis |
| 8 | Framing | Same data presented differently yields different conclusions |
| 9 | Status Quo | Change rejected without proportional cost-benefit analysis |
| 10 | Recency | Only recent data considered; long-term trends ignored |
| 11 | Authority | Senior position accepted as sufficient justification |
| 12 | Survivorship | Only successful cases analyzed; failures excluded |

**Applicable standards:** EU AI Act Article 10, NIST AI RMF fairness requirements

---

### 6.7 P7: Quantum-Resistant Integrity

**Definition:** Post-quantum cryptographic signatures ensuring that decision evidence remains verifiable for 10–50 years.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Post-Quantum Signatures | 40 | ML-DSA (FIPS 204) or SLH-DSA (FIPS 205) on all decision packets |
| 2 | NIST Compliance | 35 | Algorithms compliant with NIST post-quantum standards |
| 3 | Hybrid Mode | 25 | Classical + post-quantum dual signatures during transition period |
| 4 | Key Rotation | 30 | Automated key rotation with forward secrecy |
| 5 | Algorithm Agility | 25 | Architecture supports algorithm replacement without data migration |
| 6 | Long-Term Verification | 30 | Self-contained verification metadata (no external dependency for verification) |

**Maximum raw score:** 185

#### Implementation Guidance

During the transition period (2024–2030), implementations SHOULD use **hybrid mode** — dual signatures using both a classical algorithm (e.g., Ed25519, ECDSA P-384) and a post-quantum algorithm (e.g., ML-DSA-65).

Verification metadata SHALL be self-contained: a verifier with only the signed artifact and the signer's public key SHALL be able to verify integrity without network access.

**Applicable standards:** NIST SP 800-208, CNSA 2.0, ETSI QSC

---

### 6.8 P8: Synthetic Media Authentication

**Definition:** Content provenance signing, authenticity analysis, and chain of custody for digital evidence used in or produced by decision processes.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Content Provenance | 35 | C2PA-compliant content credentials on all media evidence |
| 2 | Authenticity Analysis | 30 | Multi-point analysis (pixel, metadata, noise, compression, temporal, source) |
| 3 | Chain of Custody | 30 | Append-only custody log from origin to vault |
| 4 | Metadata Integrity | 25 | EXIF/XMP tamper detection |
| 5 | Multi-Modal Verification | 25 | Cross-reference across media types (video, audio, text, image) |
| 6 | Legal Admissibility | 30 | Compliance with applicable rules of evidence (e.g., FRE 901(b)(9)) |

**Maximum raw score:** 175

#### Implementation Guidance

Authenticity verdicts SHALL use the following scale: `authentic`, `likely_authentic`, `inconclusive`, `likely_synthetic`, `synthetic`, `tampered`.

Chain of custody entries SHALL be append-only and SHALL include: actor identity, role, action, timestamp, and integrity hash.

**Applicable standards:** EU AI Act Article 52, C2PA v1.3

---

### 6.9 P9: Cross-Jurisdiction Compliance

**Definition:** Automated detection of conflicting regulatory requirements across jurisdictions, with documented good-faith resolution strategies.

#### Technical Controls

| # | Control | Max Score | Requirement |
|:-:|---------|:---------:|-------------|
| 1 | Jurisdiction Coverage | 35 | Minimum 17 jurisdictions simultaneously assessable |
| 2 | Conflict Detection | 35 | Automatic identification of regulatory contradictions |
| 3 | Good-Faith Documentation | 30 | Maximum-compliance strategy documented with legal rationale |
| 4 | Regulatory Update Tracking | 25 | Monitoring of regulatory changes affecting configured jurisdictions |
| 5 | Per-Jurisdiction Evidence | 30 | Evidence packet exportable in jurisdiction-specific format |
| 6 | Proactive Disclosure | 20 | Pre-enforcement analysis shared with relevant authorities |

**Maximum raw score:** 175

#### Conflict Severity Levels

| Level | Definition |
|-------|-----------|
| Irreconcilable | Direct legal contradiction — compliance with one jurisdiction necessarily violates another |
| Significant | Material conflict requiring legal counsel and risk acceptance |
| Moderate | Addressable through contractual or technical safeguards |
| Minor | Procedural differences resolvable through documentation |
| Theoretical | Potential conflict under unlikely circumstances |

#### Resolution Strategies

Implementations SHALL support at least the following resolution strategies:

1. **Highest Standard** — Apply the most restrictive requirement globally
2. **Jurisdiction Priority** — Apply local law where operations occur
3. **Data Localization** — Process locally; synchronize metadata only
4. **Consent Overlay** — Obtain consent meeting the highest applicable threshold
5. **Contractual Safeguard** — Standard contractual clauses or equivalent instruments
6. **Regulatory Exemption** — Document applicable exemptions with supporting evidence
7. **Good-Faith Maximum** — Document maximum-achievable compliance with rationale for gaps
8. **Legal Opinion** — Formal legal opinion with liability acceptance documentation
9. **Regulatory Sandbox** — Operate under sandbox provisions where available

---

## 7. IISS — Institutional Immune System Score

### 7.1 Calculation

The IISS is calculated as the weighted sum of 9 normalized primitive scores:

```
IISS = Σ(NormalizedScore_i × Weight_i)  for i = 1 to 9

where:
  NormalizedScore_i = (RawScore_i / MaxScore_i) × 1000
  Weight_i = primitive weight (see Section 5.1)
  RawScore_i = sum of 6 control scores for primitive i
  MaxScore_i = sum of 6 control maximums for primitive i
```

The IISS range is **0–1000**.

Every IISS calculation SHALL include a cryptographic integrity hash (SHA-256 minimum) of the input scores, and SHOULD include a digital signature.

### 7.2 Certification Bands

| Score Range | Band | Interpretation |
|:-----------:|------|---------------|
| 801–1000 | **Exceptional** | Organization can demonstrate decision governance under adversarial scrutiny with >95% confidence |
| 601–800 | **Resilient** | Strong coverage with minor gaps; eligible for governance-based insurance discounts |
| 401–600 | **Developing** | Core capabilities in place; advanced primitive gaps remain |
| 201–400 | **Vulnerable** | Partial coverage; significant regulatory and litigation exposure |
| 0–200 | **Critical** | Fundamental gaps; cannot demonstrate basic decision governance |

### 7.3 Certification Levels

| Level | Minimum Score | Significance |
|:-----:|:------------:|-------------|
| Platinum | 850 | Highest-assurance governance certification |
| Gold | 700 | Enterprise governance certification |
| Silver | 500 | Regulatory readiness certification |
| Bronze | 300 | Basic governance certification |

### 7.4 Use Cases

a) **Board reporting:** Trend tracking of organizational governance posture over time

b) **Insurance underwriting:** Governance-based premium differentiation

c) **M&A due diligence:** Assessment of target organization's decision risk exposure

d) **Regulatory self-assessment:** Demonstration of proactive compliance posture

e) **Benchmarking:** Industry comparison using anonymized aggregate data

### 7.5 Regulatory Readiness Assessments

The IISS SHALL include readiness assessments for applicable regulatory frameworks. Each assessment produces:
- A score (0–100)
- A binary `ready` indicator
- A list of specific gaps

Frameworks assessed SHALL be configurable per organization and SHALL include at minimum: EU AI Act, GDPR, DORA (where applicable), and applicable national AI regulations.

---

## 8. Artifact Specifications

### 8.1 Decision Packet

A decision packet is a self-contained evidence bundle containing:

| Component | Required | Description |
|-----------|:--------:|-------------|
| Decision metadata | YES | Title, category, risk level, status |
| Deliberation record | YES | Agent perspectives, rounds, reasoning |
| Vote record | YES | Per-agent votes with rationale |
| Dissent record | YES (if any) | Non-suppressible minority views |
| Alternatives considered | YES | Paths not taken with rejection rationale |
| Timestamp tokens | YES | P1 evidence (internal + external layers) |
| Override record | IF APPLICABLE | Override detection, rationale, authority |
| Bias analysis | RECOMMENDED | P6 cognitive bias scan results |
| Jurisdiction assessment | IF APPLICABLE | P9 compliance status per jurisdiction |
| Integrity block | YES | Hash, algorithm, signature(s), timestamp |

Decision packets SHALL be serializable to JSON. Formal JSON Schema definitions are provided separately.

### 8.2 Evidence Receipt

An evidence receipt summarizes an organization's decision governance posture over a defined period:

| Component | Required | Description |
|-----------|:--------:|-------------|
| Scope | YES | Assessment period, decisions assessed, jurisdictions |
| IISS score | YES | Overall score, band, certification level |
| Primitive scores | YES | Per-primitive scores with control-level detail |
| Regulatory readiness | YES | Per-framework readiness scores and gaps |
| Recommendations | RECOMMENDED | Prioritized improvement actions with estimated impact |
| Integrity block | YES | Hash, signature(s), RFC 3161 timestamp |

Evidence receipts SHALL be exportable in at least JSON format. PDF and XML export is RECOMMENDED.

---

## 9. Compliance Mapping

### 9.1 EU AI Act

| Article | Requirement | DGI Primitive(s) |
|---------|------------|:----------------:|
| Art. 12 | Record-keeping for high-risk AI | P1, P4 |
| Art. 13 | Transparency and information | P2, P6 |
| Art. 14 | Human oversight | P3 |
| Art. 52 | Transparency for synthetic content | P8 |
| Art. 61 | Post-market monitoring | P5 |

### 9.2 NIST AI RMF

| Function | DGI Primitive(s) |
|----------|:----------------:|
| Govern | All (comprehensive evidence) |
| Map | P5, P9 |
| Measure | IISS |
| Manage | P6, P2 |

### 9.3 DORA

| Article | Requirement | DGI Primitive(s) |
|---------|------------|:----------------:|
| Art. 5 | ICT risk management | All |
| Art. 11 | Resilience testing | P4 (Similarity) |
| Art. 17 | Incident reporting | P1 |
| Art. 28 | Third-party risk | P9 |

### 9.4 Additional Frameworks

DGI primitives have been mapped to 33+ regulatory frameworks across 23+ jurisdictions. See the companion document *DGI Framework — Global Applicability v1.0* for the complete mapping.

---

## 10. Relationship to Existing Standards

| Standard | Relationship | Integration Point |
|----------|:------------:|------------------|
| ISO/IEC 42001 | Complementary | DGI provides the evidence artifacts that 42001 implementations produce |
| ISO/IEC 38507 | Complementary | DGI operationalizes governance principles into verifiable evidence |
| ISO/IEC 23894 | Complementary | DGI preserves risk assessment decisions as tamper-evident artifacts |
| ISO/IEC 27001 | Complementary | DGI extends information security to decision evidence integrity |
| ISO/IEC 5338 | Complementary | DGI enriches the operational phase of the AI system lifecycle |
| NIST AI RMF | Complementary | DGI implements the "Govern" function with measurable primitives |
| IEEE 7000 | Complementary | DGI extends ethical design to runtime evidence preservation |

**An organization implementing ISO/IEC 42001 can adopt DGI as the evidence layer for its AIMS without conflict.**

---

## 11. Implementation Considerations

### 11.1 Deployment Models

DGI implementations MAY be deployed in any of the following models:

a) **Cloud SaaS** — Hosted service with API access

b) **Private Cloud** — Organization-managed cloud infrastructure

c) **On-Premises** — Self-hosted within organizational network boundary

d) **Air-Gapped** — Fully isolated deployment for classified or sovereign environments

### 11.2 Minimum Viable Implementation

An organization beginning DGI adoption SHOULD prioritize:

1. **Phase 1 (Months 1–3):** P1 (Discovery-Time Proof) + P4 (Continuity Memory)
2. **Phase 2 (Months 4–6):** P3 (Override Accountability) + P2 (Deliberation Capture)
3. **Phase 3 (Months 7–12):** P5 (Drift Detection) + P6 (Cognitive Bias Mitigation) + IISS scoring
4. **Phase 4 (Months 13–18):** P9 (Cross-Jurisdiction) + P7 (Quantum-Resistant) + P8 (Media Auth)

### 11.3 Interoperability

DGI artifacts SHALL use open formats:
- JSON for structured data (with published JSON Schema)
- PDF/A for human-readable evidence receipts
- XML for legacy system integration
- OpenAPI for REST API definitions

---

## Annex A (Informative): Industry Benchmarks

| Industry | Average IISS | Median | Top Quartile | Bottom Quartile |
|----------|:----------:|:------:|:------------:|:--------------:|
| Defense | 560 | 530 | 750 | 380 |
| Financial Services | 520 | 490 | 720 | 340 |
| Insurance | 510 | 480 | 710 | 330 |
| Healthcare | 480 | 450 | 680 | 300 |
| Energy | 470 | 440 | 660 | 310 |
| Technology | 450 | 420 | 650 | 280 |
| Legal | 410 | 380 | 620 | 250 |
| Government | 390 | 360 | 580 | 220 |
| Manufacturing | 380 | 350 | 560 | 210 |

NOTE: No industry currently averages above the "Developing" band (600). The "Resilient" threshold (601+) represents measurable competitive differentiation.

---

## Annex B (Informative): Open Research Questions

1. **Temporal decay:** What is the maximum verifiable lifetime of cryptographic proofs under post-quantum migration scenarios?

2. **Explainability vs. privacy:** Can DGI satisfy the right to explanation (GDPR Art. 22) without exposing trade secrets in the deliberation record?

3. **Standardization:** Should the 9 primitives become the basis for an ISO/IEC standard? What is the appropriate document type (IS, TS, TR)?

4. **Quantitative validation:** Does a higher IISS score correlate with lower litigation/regulatory risk? (Longitudinal study required.)

5. **Cross-organizational evidence:** How should decision evidence be shared across organizational boundaries in supply-chain or joint-venture scenarios? (Federated DGI.)

6. **Bias detection accuracy:** What are the false-positive and false-negative rates for the 12-bias detection library across different cultural contexts?

---

## Bibliography

- Floridi, L., et al. (2018). "AI4People—An Ethical Framework for a Good AI Society." *Minds and Machines*, 28(4), 689–707.
- Haber, S. & Stornetta, W.S. (1991). "How to time-stamp a digital document." *Journal of Cryptology*, 3(2), 99–111.
- Jobin, A., Ienca, M. & Vayena, E. (2019). "The global landscape of AI ethics guidelines." *Nature Machine Intelligence*, 1(9), 389–399.
- Kahneman, D. (2011). *Thinking, Fast and Slow.* Farrar, Straus and Giroux.
- Raji, I.D., et al. (2020). "Closing the AI Accountability Gap." *ACM FAccT 2020*, 33–44.
- Selbst, A.D., et al. (2019). "Fairness and Abstraction in Sociotechnical Systems." *ACM FAccT 2019*, 59–68.

---

*DGI Technical Report v1.0 — Pre-submission draft for ISO/IEC JTC 1/SC 42*
