# CrisisChain

> **Transparent, on-chain humanitarian aid from donor wallet to field NGO, instantly verifiable.**

---

## 🌍 Vision

Humanitarian aid often fails not because people don't want to help, but because the systems that move aid are slow, opaque, and bureaucratic. Donations pass through multiple intermediaries, funds are delayed for weeks through international wire transfers, and donors rarely see where their money actually goes.

CrisisChain fixes this. It is a **Web3 infrastructure layer** for humanitarian crowdfunding and transparent aid delivery — creating direct pipelines between donors and responders, powered by transparent ledgers and programmable payments.

---

## ◈ What It Does

| Feature | Description |
|---------|-------------|
| **Direct Donations** | Donors contribute USDC directly to regional crisis funds, on-chain — no intermediaries |
| **NGO Reimbursement** | NGOs upload receipts after purchasing supplies; verified reimbursements settle instantly |
| **Proof-of-Delivery** | Multi-signal verification (OCR + geo-check + peer attestation) before funds are released |
| **Crisis Intelligence** | Live data from ACLED, HDX HAPI, and ReliefWeb auto-deploys funding pools for escalating crises |
| **Full Transparency** | Every donation, receipt, and reimbursement is recorded on-chain and publicly verifiable |

---

## 💡 Inspiration

If the infrastructure for moving money globally already exists through blockchain networks — why isn't humanitarian aid using it?

CrisisChain was built from that question. We wanted a system where:
- Donors fund humanitarian response **directly**
- NGOs receive funds **without waiting on intermediaries**
- Every step of the process is **transparent and verifiable**

---

## 🔧 How We Built It

### Blockchain Layer
- **Solidity smart contracts** managing crisis funding pools and automated reimbursements
- Deployed with **Foundry**, using an ERC-20 USDC-style token for stable donations

### Verification System — Proof-of-Delivery
- OCR analysis of uploaded receipts
- Geographic verification of delivery locations
- Peer NGO attestations
- Beneficiary confirmation

Funds are released only when a **verification threshold (2 of 4 signals)** is met.

### Backend Services
- **Rust indexer** (Axum + Alloy) — tracks on-chain events, syncs to PostgreSQL
- **FastAPI services** — crisis intelligence, AI summaries, OCR receipt verification
- **Express API gateway** — connects web interface to blockchain
- **Python data pipeline** — ingests ACLED, HDX HAPI, ReliefWeb humanitarian data

### Frontend
- **Next.js + TypeScript** — fast, modern interface
- **wagmi + viem + RainbowKit** — wallet connectivity
- **react-globe.gl + Three.js** — live 3D global crisis visualization

### Infrastructure
- Fully **Dockerized** microservices simulates complete end-to-end pipeline

---

## 🚧 Challenges

**Making crypto invisible**
Humanitarian responders shouldn't need to understand gas fees or private keys. We stripped all blockchain terminology from NGO-facing flows — they see funds, receipts, and reimbursements, not contracts and transactions.

**Designing trust without re-centralization**
A single verification oracle is a dangerous central failure point. Our multi-signal model requires a threshold of independent signals, reducing fraud risk while keeping the system decentralized.

**Turning humanitarian data into automated action**
ACLED, HDX, and ReliefWeb have different formats, region identifiers, and severity indicators. We built a normalization pipeline that converts these heterogeneous signals into a unified severity score capable of auto-triggering on-chain funding pools.

---

## 🏆 Accomplishments

- Full end-to-end prototype connecting donors, NGOs, crisis data, and blockchain in one system
- Multi-signal verification model for humanitarian reimbursements
- Real humanitarian data sources integrated into an automated funding pipeline
- All donations, purchases, and reimbursements transparently visible on-chain
- Complete working system shipped in a single hackathon weekend

---

## 📖 What We Learned

The barrier to blockchain adoption is rarely the technology it is the user experience. If a system requires understanding private keys or network configurations, it will never be adopted by humanitarian organizations working in crisis environments.

The data for crisis response already exists. The missing piece is the infrastructure that can act on it automatically. CrisisChain showed us this automation layer is achievable even in a short development cycle.

---

## 🚀 What's Next

- **Geotracking + photo verification** of deliveries to reduce receipt fraud
- **Real stablecoin integration** on live blockchain networks (beyond testnet)
- **NGO partnership pilots** for real-world deployment
- **Expanded verification network** with more independent data sources
- **Mobile-first UX** for field responders
- **Donor analytics** deep impact tracking per contribution

Long term, CrisisChain is an **open protocol for humanitarian funding** where donors, NGOs, and data providers coordinate aid transparently and efficiently across borders.

---

## ⬢ Getting Started

### Prerequisites
- Node.js 18+
- Docker + Docker Compose
- A Web3 wallet (MetaMask or RainbowKit-compatible)

```

---

## 🛠️ Built With

`Solidity` · `Foundry` · `Rust` · `Axum` · `Alloy` · `FastAPI` · `Python` · `Express` · `Next.js` · `TypeScript` · `wagmi` · `viem` · `RainbowKit` · `Three.js` · `react-globe.gl` · `PostgreSQL` · `Docker`

---

*CrisisChain Because aid should move at the speed of need, not the speed of bureaucracy.*
