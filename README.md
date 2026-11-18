---
name: drs-base-onchain-telemetry
description: Pay-per-call x402 v2 crypto telemetry on Base mainnet (eip155:8453). Provides on-chain Base token liquidity verdicts (A-F grade, swap velocity, Llama 3.3 AI roast & shareable receipt card), real-time BTC/ETH/SOL spot prices, DEX pool liquidity depth, and x402 settlement health checks settled in native Base USDC.
version: 2.0.0
license: MIT
metadata:
 author: D.R.S
 protocol: x402-v2
 network: eip155:8453
 currency: USDC
 payout_wallet: "0x452993071FdE3743767f98f339E90D9A313BBf3B"
 tags:
 - x402
 - base
 - defi
 - crypto
 - telemetry
 - onchain
 - ai-agents
---

# D.R.S Base On-Chain Telemetry & Token Verdict Skill (x402 v2)

This skill enables autonomous AI agents to fetch real-time Base mainnet (`eip155:8453`) on-chain DEX telemetry, token liquidity risk grades, AI market roasts, and cryptocurrency spot prices using HTTP `402 Payment Required` (`x402 v2`) micropayments in native **Base USDC** (`0x833589fCD6eDb6E08f4c7C32D4f71b54bda02913`).

> **Scope & Disclaimer:** All endpoints provide informational on-chain and market telemetry only. Nothing returned by these endpoints constitutes financial, investment, or trading advice.

---

## Available Paid Endpoints (x402 v2 / Base USDC)

### 1. Base Token On-Chain Verdict & AI Roast (`$0.015 USDC`)
Inspects any Base ERC-20 token directly via on-chain smart-contract calls (`eth_call` & `eth_getLogs`) across **Uniswap v3** and **Aerodrome** pools, counts 1-hour swap velocity, computes a `0-100` liquidity/activity score and `A-F` letter grade, generates a 1-sentence Llama 3.3 70B market roast, and returns a hosted dark-mode receipt card URL.

- **Endpoint (`GET` or `POST`):** `https://drs-base-token-verdict.dangerous40-ds.workers.dev/verdict`
- **Price:** `0.015` USDC (`15000` atomic units) on Base (`eip155:8453`)
- **OpenAPI Spec:** `https://drs-base-token-verdict.dangerous40-ds.workers.dev/openapi.json`
- **Input Parameter (`token`):** Base `0x...` ERC-20 contract address or symbol shortcut (`DEGEN`, `AERO`, `BRETT`, `TOSHI`, `CBBTC`, `VIRTUAL`).

**Example `GET` Request:**
GET https://drs-base-token-verdict.dangerous40-ds.workers.dev/verdict?token=DEGEN

**Example `POST` Request:**
POST https://drs-base-token-verdict.dangerous40-ds.workers.dev/verdict
Content-Type: application/json
Body: {"token": "0x4ed4E862860beD51a9570b96d89aF5E1B0Efefed"}

---

### 2. Real-Time Crypto Spot Price Telemetry (`$0.001 USDC`)
Low-latency spot price oracle returning current USD market prices for major crypto assets (`BTC`, `ETH`, `SOL`).

- **Endpoint (`GET`):** `https://vapi-unified-node.dangerous40-ds.workers.dev/price` (also available at `/`)
- **Price:** `0.001` USDC (`1000` atomic units) on Base (`eip155:8453`)
- **OpenAPI Spec:** `https://vapi-unified-node.dangerous40-ds.workers.dev/openapi.json`

---

### 3. Live DEX Pool Liquidity & Velocity Telemetry (`$0.001 USDC`)
Returns live decentralized exchange pool liquidity depth and velocity telemetry for automated DeFi monitoring agents.

- **Endpoint (`GET`):** `https://vapi-unified-node.dangerous40-ds.workers.dev/liquidity`
- **Price:** `0.001` USDC (`1000` atomic units) on Base (`eip155:8453`)

---

### 4. Base Mainnet x402 Settlement & Latency Probe (`$0.001 USDC`)
Lightweight edge probe allowing autonomous agents to verify end-to-end Base Mainnet x402 v2 payment settlement and edge response latency before executing larger workflows.

- **Endpoint (`GET`):** `https://vapi-unified-node.dangerous40-ds.workers.dev/health`
- **Price:** `0.001` USDC (`1000` atomic units) on Base (`eip155:8453`)

---

## Free Public Companion Endpoint

- **Verdict Receipt Viewer (`GET /receipt` — Free / `$0`):**
 `https://drs-base-token-verdict.dangerous40-ds.workers.dev/receipt?id=<receipt_id>`
 Renders a shareable dark-mode HTML Verdict Card (append `&format=json` for raw JSON) for any previously settled `/verdict` call.
