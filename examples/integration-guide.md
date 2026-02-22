# DCII Integration Guide

**Version 2.1 | February 2026**

This guide provides step-by-step instructions for integrating the DCII framework into your application.

---

## Prerequisites

- REST API client (any language)
- Authentication credentials (API key or OAuth2 token)
- PostgreSQL 15+ (for self-hosted deployments)
- Node.js 20+ or Python 3.11+ (for SDK usage)

---

## Step 1: Calculate Your First IISS Score

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/iiss/calculate \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "organizationId": "your-org-id",
    "assessmentType": "full",
    "includeRecommendations": true
  }'
```

**Response:**
```json
{
  "id": "score-uuid",
  "score": 620,
  "band": "resilient",
  "certificationLevel": "silver",
  "primitives": {
    "P1": { "normalizedScore": 780, "weight": 0.15, "weightedContribution": 117.0 },
    "P2": { "normalizedScore": 650, "weight": 0.15, "weightedContribution": 97.5 },
    "...": "..."
  },
  "recommendations": [
    {
      "priority": "high",
      "primitive": "P7",
      "description": "Enable post-quantum signatures on decision packets",
      "estimatedImpact": 45
    }
  ]
}
```

---

## Step 2: Create a Decision Packet

Every AI-assisted decision should produce a Decision Packet conforming to the [`decision-packet.json`](../schemas/decision-packet.json) schema.

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/decisions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "decision": {
      "title": "Approve vendor contract renewal",
      "category": "operational",
      "riskLevel": "medium"
    },
    "deliberation": {
      "agents": [
        { "role": "CFO", "perspective": "Cost analysis..." },
        { "role": "Legal", "perspective": "Contract terms review..." },
        { "role": "CTO", "perspective": "Technical capability assessment..." }
      ]
    }
  }'
```

The platform will automatically:
1. Assign 3+ AI agent perspectives (P2)
2. Capture deliberation in real-time (P2)
3. Apply RFC 3161 timestamps (P1)
4. Run 12-bias cognitive scan (P6)
5. Check jurisdiction compliance (P9)
6. Generate integrity hash and signatures (P7)

---

## Step 3: Timestamp Critical Events

For high-stakes decisions, add explicit timestamps with external verification:

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/timestamp/issue \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "data": "SHA-256 hash of the event data",
    "layers": ["internal", "rfc3161", "blockchain"],
    "blockchainTarget": "ethereum-mainnet",
    "referenceId": "decision-packet-uuid",
    "referenceType": "decision"
  }'
```

---

## Step 4: Run Bias Analysis

Analyze any deliberation for cognitive biases:

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/bias/analyze \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "deliberationId": "session-uuid",
    "organizationId": "your-org-id",
    "analysisDepth": "comprehensive"
  }'
```

**Response includes:**
- Per-bias risk levels (12 biases scanned)
- Rubber-stamp detection
- Groupthink indicators
- Recommended mitigations
- SHA-256 integrity hash of the analysis

---

## Step 5: Generate a Regulator's Receipt™

Export a court-admissible evidence package:

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/iiss/receipt \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "organizationId": "your-org-id",
    "format": "pdf",
    "periodStart": "2026-01-01T00:00:00Z",
    "periodEnd": "2026-03-31T23:59:59Z",
    "jurisdictions": ["US Federal", "EU"],
    "includeDecisionPackets": true
  }'
```

Available formats: `pdf`, `json`, `xml`

The receipt conforms to the [`regulators-receipt.json`](../schemas/regulators-receipt.json) schema.

---

## Step 6: Monitor Compliance Drift

Set up continuous monitoring:

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/drift/configure \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "organizationId": "your-org-id",
    "frameworks": ["GDPR", "SOC2", "EU_AI_ACT"],
    "alertThresholds": {
      "warning": 0.05,
      "critical": 0.15
    },
    "webhookUrl": "https://your-app.com/webhooks/dcii-drift"
  }'
```

---

## Step 7: Search Similar Decisions

Before making a new decision, search for historical precedents:

```bash
curl -X POST https://api.datacendia.com/api/v1/dcii/similarity/search \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "query": "Vendor contract renewal for cloud infrastructure provider",
    "organizationId": "your-org-id",
    "dimensions": ["semantic", "contextual", "outcome"],
    "minStrength": "moderate",
    "limit": 10
  }'
```

**Response includes:**
- Ranked matches with similarity scores
- Historical outcomes and lessons learned
- Dissenter accuracy rates
- Pattern detection (recurring failures, override patterns)

---

## Webhook Integration

Configure webhooks to receive real-time notifications. See [`webhook-spec.md`](../api/webhook-spec.md) for event types and payload schemas.

---

## SDK Support

| Language | Package | Status |
|----------|---------|--------|
| Node.js/TypeScript | `@datacendia/dcii-sdk` | Available |
| Python | `datacendia-dcii` | Available |
| Java | `com.datacendia:dcii-sdk` | Coming Q3 2026 |
| .NET | `Datacendia.DCII` | Coming Q3 2026 |

---

## Self-Hosted Deployment

For organizations requiring on-premises or air-gapped deployment:

1. Deploy PostgreSQL 15+ with the DCII schema
2. Configure the DCII services (6 microservices)
3. Set up PostQuantumKMS for cryptographic operations
4. Configure external TSA providers (optional)
5. Set up Qdrant for similarity search (optional)

See the [Deployment Guide](https://docs.datacendia.com/deployment) for detailed instructions.

---

## Support

- **Documentation:** https://docs.datacendia.com
- **API Reference:** See [`api-spec.yaml`](../api/api-spec.yaml)
- **GitHub Issues:** https://github.com/datacendia/dcii-framework/issues

---

*DCII Framework v2.1 — Datacendia, LLC*
