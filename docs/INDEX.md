# Documentation Index

**Last Updated:** March 2026  
**Purpose:** Canonical source map for all DGI/DCII documentation. Prevents confusion from overlapping documents.

## How to Use This Index

Each topic has **one canonical source**. Superseded documents have deprecation headers pointing here. When adding or updating documentation, check this index first to avoid creating duplicate coverage.

---

## Canonical Sources

| Topic | Canonical Document | Status |
|-------|-------------------|--------|
| **DDGI Framework Specification** | [`../DGI-Framework-v1.0.md`](../DGI-Framework-v1.0.md) | Normative v1.0 |
| **DCII Implementation Reference** | [`../README.Implementation.md`](../README.Implementation.md) | Informative v2.1 |
| **Gap Analysis (ISO Standards)** | [`ISO-GAPS-IN-EXISTING-STANDARDS.md`](ISO-GAPS-IN-EXISTING-STANDARDS.md) | Canonical — merges gap analysis + non-duplication proof |
| **Scope Boundaries** | [`SCOPE-BOUNDARIES.md`](SCOPE-BOUNDARIES.md) | Canonical |
| **Global Regulatory Equivalence** | [`GLOBAL-REGULATORY-EQUIVALENCE.md`](GLOBAL-REGULATORY-EQUIVALENCE.md) | Canonical |
| **Compliance Mapping** | [`compliance-mapping.md`](compliance-mapping.md) | Canonical |
| **Primitive Specifications** | [`primitive-specifications.md`](primitive-specifications.md) | Canonical |
| **Traceability Matrix** | [`TRACEABILITY-MATRIX.md`](TRACEABILITY-MATRIX.md) | Canonical |
| **Standards Body Engagement** | [`standards-body-engagement.md`](standards-body-engagement.md) | Canonical |
| **Contributors** | [`DGI-Contributors.md`](DGI-Contributors.md) | Canonical |
| **DCII Full Paper** | [`DCII_Framework_v2.1.md`](DCII_Framework_v2.1.md) | Informative — detailed implementation paper |

## Superseded Documents

These documents are **superseded** by canonical sources above. They are preserved for reference but should not be updated or cited. Each has a deprecation header added.

| Superseded Document | Superseded By | Reason |
|--------------------|--------------|--------|
| `DGI-Framework-GapAnalysis-v1.0.md` | `ISO-GAPS-IN-EXISTING-STANDARDS.md` | Duplicate gap analysis — same standards, same conclusions |
| `NON-DUPLICATION-PROOF.md` | `ISO-GAPS-IN-EXISTING-STANDARDS.md` | Subset of gap analysis — non-duplication proof is part of ISO gaps doc |
| `DGI-Framework-GlobalApplicability-v1.0.md` | `GLOBAL-REGULATORY-EQUIVALENCE.md` | Duplicate regulatory equivalence mapping |
| `DGI-Framework-Contributors-v1.0.md` | `DGI-Contributors.md` | Duplicate contributors register |
| `DGI_Framework_v2.md` | `../DGI-Framework-v1.0.md` | Earlier draft superseded by root-level v1.0 |
| `DGI-TR-v1.0.md` | `../README.Implementation.md` + `DCII_Framework_v2.1.md` | Technical report content merged into implementation docs |

## Adding New Documentation

1. Check this index — does a canonical doc already cover the topic?
2. If yes, update the existing canonical doc
3. If no, create the new doc and add it to this index
4. Never create a doc with a topic that overlaps an existing canonical source
