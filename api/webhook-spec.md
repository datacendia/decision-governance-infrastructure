# DCII Webhook Specification

**Version 2.1 | February 2026**

This document describes the webhook events emitted by the DCII platform for real-time integration.

---

## Configuration

Register a webhook endpoint via the API:

```bash
POST /api/v1/dcii/webhooks/register
{
  "url": "https://your-app.com/webhooks/dcii",
  "events": ["iiss.score.calculated", "bias.detected", "drift.alert"],
  "secret": "your-webhook-signing-secret"
}
```

All webhook payloads are signed with HMAC-SHA256 using your secret. Verify the `X-DCII-Signature` header before processing.

---

## Event Types

### IISS Events

| Event | Trigger |
|-------|---------|
| `iiss.score.calculated` | New IISS score calculated |
| `iiss.band.changed` | Organization's IISS band changed (e.g., developing → resilient) |
| `iiss.certification.achieved` | New certification level reached |

### Bias Events (P6)

| Event | Trigger |
|-------|---------|
| `bias.detected` | Cognitive bias detected in deliberation |
| `bias.critical` | Critical-severity bias detected |
| `bias.mitigated` | Bias mitigation applied |
| `bias.rubber_stamp` | Rubber-stamp decision detected |
| `bias.groupthink` | Groupthink pattern detected |

### Timestamp Events (P1)

| Event | Trigger |
|-------|---------|
| `timestamp.issued` | New timestamp token created |
| `timestamp.verified` | Timestamp verification completed |
| `timestamp.blockchain.anchored` | Merkle root anchored to blockchain |

### Drift Events (P5)

| Event | Trigger |
|-------|---------|
| `drift.warning` | Compliance drift warning threshold exceeded |
| `drift.critical` | Compliance drift critical threshold exceeded |
| `drift.resolved` | Drift condition resolved |

### Override Events (P3)

| Event | Trigger |
|-------|---------|
| `override.detected` | Human override of AI recommendation detected |
| `override.escalated` | High-risk override auto-escalated |

### Jurisdiction Events (P9)

| Event | Trigger |
|-------|---------|
| `jurisdiction.conflict.detected` | Regulatory conflict identified |
| `jurisdiction.good_faith.generated` | Good-faith document generated |

### Media Events (P8)

| Event | Trigger |
|-------|---------|
| `media.signed` | Media asset signed with C2PA provenance |
| `media.synthetic.detected` | Potential synthetic media detected |

### Similarity Events

| Event | Trigger |
|-------|---------|
| `similarity.pattern.detected` | Decision pattern detected (recurring failure, etc.) |
| `similarity.high_risk.match` | New decision matches high-risk historical pattern |

---

## Payload Format

All webhooks use the following envelope:

```json
{
  "id": "evt-uuid",
  "type": "iiss.score.calculated",
  "timestamp": "2026-02-22T14:30:00Z",
  "organizationId": "org-uuid",
  "data": {
    "...event-specific payload..."
  },
  "integrity": {
    "hash": "sha256-of-data",
    "signature": "hmac-sha256-of-payload"
  }
}
```

### Example: `iiss.score.calculated`

```json
{
  "id": "evt-a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "type": "iiss.score.calculated",
  "timestamp": "2026-02-22T14:30:00Z",
  "organizationId": "org-12345678-abcd-efgh-ijkl-mnopqrstuvwx",
  "data": {
    "scoreId": "score-uuid",
    "score": 720,
    "previousScore": 680,
    "band": "resilient",
    "certificationLevel": "gold",
    "change": "+40",
    "topRecommendation": "Enable post-quantum signatures on decision packets (+45 estimated)"
  }
}
```

### Example: `bias.critical`

```json
{
  "id": "evt-b2c3d4e5-f6a7-8901-bcde-f12345678901",
  "type": "bias.critical",
  "timestamp": "2026-02-22T15:00:00Z",
  "organizationId": "org-12345678-abcd-efgh-ijkl-mnopqrstuvwx",
  "data": {
    "analysisId": "analysis-uuid",
    "deliberationId": "delib-uuid",
    "biasType": "groupthink",
    "severity": "critical",
    "evidence": "All 5 agents voted unanimously within 30 seconds with no debate recorded",
    "recommendedAction": "Require devil's advocate challenge before finalizing"
  }
}
```

### Example: `drift.critical`

```json
{
  "id": "evt-c3d4e5f6-a7b8-9012-cdef-123456789012",
  "type": "drift.critical",
  "timestamp": "2026-02-22T16:00:00Z",
  "organizationId": "org-12345678-abcd-efgh-ijkl-mnopqrstuvwx",
  "data": {
    "framework": "GDPR",
    "control": "Data retention policy",
    "baseline": 0.95,
    "current": 0.72,
    "deviation": 0.23,
    "threshold": 0.15,
    "recommendedAction": "Review data retention settings — 23% drift from baseline exceeds 15% critical threshold"
  }
}
```

---

## Retry Policy

- Failed deliveries are retried with exponential backoff: 10s, 30s, 1m, 5m, 15m, 1h
- Maximum 6 retry attempts
- After 6 failures, the webhook is marked as `failing` and an email alert is sent
- Successful delivery requires HTTP 2xx response within 10 seconds

---

## Security

- All payloads signed with HMAC-SHA256 via `X-DCII-Signature` header
- Verify signature before processing: `HMAC-SHA256(payload, secret) === header`
- Webhook URLs must use HTTPS
- IP allowlist available for enterprise deployments

---

*DCII Framework v2.1 — Datacendia, LLC*
