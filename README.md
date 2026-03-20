# ghostguards

> GPS spoofing and coordinated delivery fraud detection using multi-signal consensus and graph-based ring analysis.

---

## The Problem

Every fraud detection system trusts GPS. Fraud rings exploit that.

A coordinated attack doesn't just spoof one account — it runs dozens simultaneously, sharing the same devices, IP pools, and payout endpoints. Individually, each account looks normal. Collectively, it's an organized operation that standard GPS validation cannot see.

---

## What GhostGuard Does

GhostGuard eliminates single-point trust entirely.

Instead of asking *"is this GPS real?"*, it asks *"does this user behave like reality itself?"*

Ground truth is established only when five independent signal dimensions agree. When they don't — or when they align in statistically impossible ways — fraud is flagged.

---

## Architecture

GhostGuard runs four independent detection layers in parallel:

```
[ Data Collection ]
        ↓
[ Signal Validation Layer ]
        ↓
[ Behavioral Analysis Engine ]
        ↓
[ Graph Fraud Detection ]
        ↓
[ Risk Scoring Engine ]
        ↓
[ Decision & UX Handling ]
```

### 1. Signal Validation Layer
Cross-references GPS against:
- Accelerometer and gyroscope data — static sensors + moving GPS = spoofing
- IP geolocation — GPS in City A, IP resolving to City B = anomaly
- Cell tower triangulation — independent location corroboration
- Speed and path realism — teleportation patterns flagged against road networks

### 2. Behavioral Analysis Engine
Builds per-user activity profiles and flags:
- 24/7 activity with no natural breaks
- Perfectly repeated delivery patterns
- Zero-latency responses to platform events
- Session timing inconsistencies

### 3. Graph Fraud Detection
Constructs a dynamic relationship graph:
- **Nodes** — individual accounts
- **Edges** — shared attributes (device ID, IP address, payment method, location overlap)

Fraud rings emerge as dense clusters with synchronized activity bursts. 50 accounts sharing 3 payout endpoints, active simultaneously — statistically impossible by chance.

### 4. Risk Scoring Engine
Aggregates all signals into a continuous, dynamic risk score:

| Risk Level | Action |
|---|---|
| Low | Normal processing |
| Medium | Silent monitoring |
| High | Payout delay + verification request |
| Critical | Temporary freeze + investigation |

---

## Signal Dimensions

| # | Dimension | Signals |
|---|---|---|
| 1 | Location Intelligence | GPS traces, route matching, location entropy |
| 2 | Network Signals | IP/ASN patterns, cell tower IDs, network-switch anomalies |
| 3 | Device Fingerprinting | Device ID hash, OS integrity, emulator detection |
| 4 | Behavioral Patterns | Delivery frequency, session timing, action latency |
| 5 | Financial Linkages | Shared wallets, payout clustering, bank account reuse |

---

## UX Balance

A security system that punishes genuine workers is itself a failure.

- **Multi-signal requirement** — no single anomaly ever triggers action
- **Grace thresholds** — real-world imperfections (GPS dropout, network drops) are tolerated
- **Soft interventions first** — verification requests before any hard action
- **Explainability logs** — every flag has a full reason trail
- **Appeal mechanism** — flagged users can contest with human review

---

## Tech Stack

- **Backend** — Python, FastAPI
- **Databases** — PostgreSQL (transactional), Neo4j (relationship graph), Redis (real-time scoring cache)
- **ML & Graph** — Scikit-learn, NetworkX
- **Streaming** — Apache Kafka
- **Infrastructure** — Docker, AWS Lambda

---

## Key Insight

> Fraud at scale leaves structure, not just anomalies.

Sophisticated attackers are nearly invisible at the individual level. Their shared infrastructure is not.

---

## Project Status

Phase 1 — Architecture & Design  
Built for DEVTrails Hackathon

---

## What's Next

- Personalized behavioral baselines via per-user ML models
- Financial graph expansion to detect downstream money mule networks
- Human review feedback loop retraining detection thresholds
- Trust Score API for platform-wide consumption (insurance, promotions, dispatch)
