# DCII Primitive Specifications

**Version 2.1 | February 2026**

This document provides the detailed technical specification for each of the 9 DCII primitives, including controls, scoring criteria, and implementation requirements.

---

## Scoring Methodology

Each primitive has **6 technical controls**, each scored against a defined maximum. The weighted, normalized sum produces the IISS score:

```
IISS = Σ(NormalizedPrimitiveScore_i × Weight_i) for i = 1 to 9
NormalizedScore = (Σscores / Σmaxes) × 1000
```

Every score is SHA-256 hashed and digitally signed for integrity.

---

## P1: Discovery-Time Proof (Weight: 15%)

**Definition:** Cryptographic proof of when information became known and decisions were made, preventing backdating and post-hoc rationalization.

**The Question:** *"When did you know?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Cryptographic Timestamping | 40 | RFC 3161 compliant timestamps on all decision events |
| Event Linkage | 30 | Timestamps linked to deliberation records |
| Tamper Evidence | 40 | Merkle tree integrity with independent verification |
| Non-Repudiation | 30 | Digital signatures with delivery proof |
| Blockchain Anchoring | 20 | Optional external anchoring for highest-stakes decisions |
| Evidence Packet Generation | 40 | One-click regulator-ready evidence export |

### Implementation Requirements

Three-layer defense-in-depth:

- **Layer 1 — Internal:** Server clock with NTP sync, SHA-256/384/512/SHA3-256, digital signature, accuracy metadata
- **Layer 2 — External RFC 3161:** Multi-provider TSA (DigiCert, Comodo, FreeTSA, GlobalSign, Entrust), full RFC 3161 token, TSA certificate chain validation. Standards: RFC 3161, RFC 3628, ETSI EN 319 421
- **Layer 3 — Blockchain:** Bitcoin mainnet/testnet, Ethereum mainnet/Goerli, Polygon. Merkle root anchoring with proof path

**Compliance:** eIDAS Article 41, ISO/IEC 18014, EU AI Act Article 12
**Targets:** Verification 100%, TSA latency <2s

---

## P2: Deliberation Capture (Weight: 15%)

**Definition:** Complete, immutable record of all perspectives considered, alternatives evaluated, and trade-offs made.

**The Question:** *"What did you consider?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Multi-Agent Analysis | 40 | Minimum 3 perspectives per decision |
| Real-Time Capture | 35 | Captured as it occurs, not retrospectively |
| Alternative Documentation | 30 | Paths not taken documented with rationale |
| Immutable Record | 35 | Hash-locked on finalization |
| Contextual Completeness | 30 | Data inputs, tools, constraints, assumptions |
| Dissent Preservation | 30 | Non-suppressible minority views |

### Implementation Requirements

- Multi-agent analysis (3+ AI perspectives)
- Real-time vote/reasoning capture
- Hash-lock on finalization
- Protected dissent records
- Export as PDF/JSON/XML

**Compliance:** EU AI Act Articles 13–14, NIST AI RMF, FDA PCCP
**Targets:** >95% factors captured, export <30s

---

## P3: Override Accountability (Weight: 12%)

**Definition:** Automatic detection and immutable preservation of instances where humans override AI recommendations.

**The Question:** *"Who decided — and why?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Automatic Override Detection | 35 | Detects when recommendation not followed |
| Mandatory Rationale Capture | 35 | Cannot proceed without explanation |
| Authority Tracking | 30 | Chain of command documented |
| Non-Suppressibility | 40 | Staff recommendations cannot be deleted |
| Time-Lock Protection | 30 | Immutable after decision |
| Escalation Workflows | 30 | High-risk overrides auto-escalated |

### Implementation Requirements

- RSA-4096/ECDSA P-384 digital signatures
- HSM/cloud KMS support
- Key rotation with chain-of-custody

**Compliance:** eIDAS (EU 910/2014), NIST SP 800-57, FDA 21 CFR Part 11
**Targets:** 100% signature verification

---

## P4: Continuity Memory (Weight: 10%)

**Definition:** Personnel-independent preservation of institutional decision knowledge with semantic retrieval.

**The Question:** *"Is knowledge preserved?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Context Preservation | 35 | Rationale, constraints, trade-offs captured |
| Personnel Independence | 30 | Records independent of individuals |
| Deterministic Replay | 35 | Bit-perfect reproducibility |
| Searchable & Linked | 30 | Semantic similarity search |
| Learning Integration | 35 | Historical precedent auto-surfaced |
| Outcome Tracking | 35 | Outcomes with lessons learned |

### Implementation Requirements

- Deterministic replay capability
- TF-IDF + vector search (e.g., Qdrant)
- 7–10 year retention minimum
- Air-gapped deployment support

**Compliance:** GDPR Article 32, HIPAA §164.312, ISO 27001 A.9
**Targets:** Retrieval <10s, zero unauthorized access

---

## P5: Drift Detection (Weight: 10%)

**Definition:** Continuous monitoring of compliance state with real-time anomaly detection.

**The Question:** *"Are you still compliant?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Continuous Monitoring | 40 | Real-time compliance status |
| Baseline Establishment | 25 | Statistical norms per control |
| Anomaly Detection | 35 | Deviation detection from baselines |
| Trend Analysis | 30 | Quarter-over-quarter projections |
| Early Warning System | 35 | Multi-threshold alerts with escalation |
| Root Cause Analysis | 35 | Automated investigation and remediation |

### Implementation Requirements

- Real-time monitoring across GDPR, SOC2, HIPAA, DORA, Basel III, CMMC, FedRAMP, NIST CSF, PCI DSS, ISO 27001
- Statistical baseline per control
- Multi-threshold alerting with escalation chains

**Compliance:** SOC2 CC7.2, DORA Article 11, ISO 27001 A.12.4
**Targets:** Detection <60s, <1% false positive rate

---

## P6: Cognitive Bias Mitigation (Weight: 10%)

**Definition:** Systematic detection and documentation of cognitive biases in human-AI decision-making.

**The Question:** *"Did you challenge assumptions?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Bias Detection Library | 35 | 12 biases tested per decision |
| Devil's Advocate Enforcement | 30 | Adversarial perspective required |
| Anchoring Detection | 25 | First-number anchoring flagged |
| Groupthink Prevention | 30 | Unanimous decisions scrutinized |
| Rubber-Stamp Detection | 25 | Fast approvals flagged |
| Bias Audit Trail | 30 | Results preserved in decision packet |

### The 12-Bias Library

| # | Bias | Detection Method |
|---|------|-----------------|
| 1 | **Anchoring** | First-number dominance, initial proposal accepted with minor changes |
| 2 | **Confirmation** | Only supporting evidence cited, contradictory data dismissed |
| 3 | **Groupthink** | Unanimous vote without debate, no dissenting opinions |
| 4 | **Availability** | Recent events cited disproportionately, base rates ignored |
| 5 | **Sunk Cost** | Past spending cited as justification |
| 6 | **Overconfidence** | No uncertainty range, single-point estimates |
| 7 | **Bandwagon** | "Everyone agrees" language, no independent analysis |
| 8 | **Framing** | Same data presented differently yields different conclusions |
| 9 | **Status Quo** | Change rejected without proportional analysis |
| 10 | **Recency** | Last quarter only, 5-year trends not referenced |
| 11 | **Authority** | Senior view accepted unchallenged |
| 12 | **Survivorship** | Failed attempts not analyzed |

**Compliance:** EU AI Act Article 10, NIST AI RMF Fairness, EEOC guidance
**Targets:** >70% detection, >30% modified

---

## P7: Quantum-Resistant Integrity (Weight: 10%)

**Definition:** Post-quantum cryptographic signatures ensuring proofs remain valid 10–50 years.

**The Question:** *"Is the proof future-proof?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Post-Quantum Signatures | 40 | Dilithium or SPHINCS+ on all packets |
| NIST Compliance | 35 | FIPS 204/205 |
| Hybrid Mode | 25 | Classical + PQ dual signatures |
| Key Rotation | 30 | Automated with forward secrecy |
| Algorithm Agility | 25 | Hot-swap without data migration |
| Long-Term Verification | 30 | Verifiable 50+ years |

### Implementation Requirements

- CRYSTALS-Dilithium (FIPS 204)
- SPHINCS+ (FIPS 205)
- Falcon (NIST Round 3)
- Hybrid Ed25519+Dilithium mode
- Algorithm-agile architecture
- Self-contained verification metadata

**Compliance:** NIST SP 800-208, CNSA 2.0, ETSI QSC
**Targets:** Verification <100ms, key rotation <5s

---

## P8: Synthetic Media Authentication (Weight: 8%)

**Definition:** C2PA-compliant authentication, deepfake detection, and chain of custody for digital evidence.

**The Question:** *"Is the evidence authentic?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| C2PA Provenance | 35 | Content Credentials on all media |
| Deepfake Detection | 30 | Pixel-level and audio analysis |
| Chain of Custody | 30 | Complete from device to vault |
| Metadata Integrity | 25 | EXIF tamper detection |
| Multi-Modal Verification | 25 | Cross-reference video/audio/text |
| Court Admissibility | 30 | FRE 901(b)(9) compliance |

### Implementation Requirements

**Signing:** C2PA manifest, SHA-256 content hash, certificate chain, origin tracking, optional TPM/HSM attestation

**Assessment:** 6 analysis types — pixel, metadata, noise, compression, temporal, source
**Verdicts:** authentic → likely_authentic → inconclusive → likely_synthetic → synthetic → tampered

**Custody:** Append-only chain with actor, role, action, timestamp, IP, device. SHA-256 per entry.

**Media types:** image, video, audio, document, screenshot, recording

**Compliance:** EU AI Act Article 52, C2PA v1.3, FRE 901(b)(9)
**Targets:** >95% accuracy, <2% false positives

---

## P9: Cross-Jurisdiction Compliance (Weight: 10%)

**Definition:** Automated detection of conflicting regulatory requirements with good-faith documentation.

**The Question:** *"Did you comply everywhere?"*

### Technical Controls

| Control | Max Score | Requirement |
|---------|-----------|-------------|
| Jurisdiction Coverage | 35 | 17+ jurisdictions simultaneously |
| Conflict Detection | 35 | Automatic contradiction identification |
| Good-Faith Documentation | 30 | Maximum-compliance strategy documented |
| Regulatory Update Tracking | 25 | Real-time change monitoring |
| Evidence Packet per Jurisdiction | 30 | Jurisdiction-specific export |
| Proactive Disclosure | 20 | Pre-enforcement analysis sharing |

### Supported Jurisdictions (23)

EU, US Federal, US-CA, US-NY, US-TX, US-VA, UK, China, Japan, Brazil, Canada, Australia, Singapore, India, South Korea, Switzerland, South Africa, UAE, Saudi Arabia, Hong Kong, Taiwan, Thailand, Indonesia

### Supported Frameworks (33)

GDPR, EU AI Act, DSA, DMA, DORA, CCPA/CPRA, HIPAA, SOX, Dodd-Frank, GLBA, FERPA, COPPA, UK GDPR, UK DPA 2018, FCA Rules, China PIPL/CSL/DSL, Japan APPI, Brazil LGPD, Canada PIPEDA, Australia Privacy Act, Singapore PDPA, India DPDPA, South Korea PIPA, Switzerland nFADP, South Africa POPIA, Basel III, CMMC, SOC2, ISO 27001, NIST CSF, PCI DSS, FedRAMP

### Conflict Severity Levels

irreconcilable, significant, moderate, minor, theoretical

### Resolution Strategies

highest_standard, jurisdiction_priority, data_localization, consent_overlay, contractual_safeguard, regulatory_exemption, good_faith_maximum, legal_opinion_based, regulatory_sandbox

**Compliance:** EU AI Act Article 4, GDPR Articles 44–50, DORA Article 28
**Targets:** >90% detection, >85% resolution accuracy

---

*DCII Framework v2.1 — Datacendia, LLC*
