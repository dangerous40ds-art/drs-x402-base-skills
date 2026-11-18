---
name: drs-base-onchain-and-research-suite
description: Pay-per-call x402 v2 AI agent toolkit on Base mainnet (eip155:8453). Provides multi-source web search, clean webpage text extraction, live crypto/tech news headlines, GitHub repo search, DeFi chain/protocol TVL, UTC clock & live FX rates, on-chain Base token liquidity verdicts (A-F grade, Llama 3.3 AI roast & receipt card), and real-time BTC/ETH/SOL spot prices settled in native Base USDC.
version: 3.0.0
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
    - web-search
    - defi
    - crypto
    - telemetry
    - ai-agents
    - mcp
---

# D.R.S Base On-Chain Telemetry & Universal Agent Research Suite (x402 v2)

This skill gives autonomous AI agents access to **10 pay-per-call x402 v2 endpoints** settled in native **Base USDC** (`0x833589fCD6eDb6E08f4c7C32D4f71b54bda02913` on `eip155:8453`)—combining high-frequency web search, webpage reading, live news, GitHub search, DeFi TVL, and UTC/FX utilities (`$0.001` USDC) with on-chain Base token verdicts and spot prices.

> **Scope & Disclaimer:** All endpoints provide informational web, market, and on-chain telemetry only. Nothing returned constitutes financial, investment, or trading advice.

---

## Part A: Universal Agent Utility & Research Hub (`$0.001 USDC` each)
**Base URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev`
**OpenAPI Spec:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/openapi.json`
**Methods:** All 6 endpoints below accept both `GET` (query parameters) and `POST` (JSON body) at `0.001` USDC (`1000` atomic units).

### 1. Multi-Source Web & Knowledge Search (`GET` / `POST /search`)
Queries Wikipedia, DuckDuckGo Instant Answers, Hacker News, and Reddit in parallel to return deduplicated titles, URLs, and snippets.
- **URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/search?q=Base+x402+agents`
- **POST Body:** `{"query": "Base x402 agents", "limit": 8}`

### 2. Clean Webpage Text Reader (`GET` / `POST /read`)
Fetches any public `http://` or `https://` URL and extracts the page title and clean plain text (up to 6,000 characters) with scripts and HTML stripped.
- **URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/read?url=https://example.com`
- **POST Body:** `{"url": "https://example.com"}`

### 3. Live Crypto & Tech News Headlines (`GET` / `POST /news`)
Returns real-time headlines and links from CoinTelegraph RSS and Hacker News live stories filtered by topic.
- **URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/news?topic=Base`
- **POST Body:** `{"topic": "Base", "limit": 8}`

### 4. GitHub Repository Search (`GET` / `POST /github`)
Searches public GitHub repositories sorted by stars, returning repo names, URLs, descriptions, star counts, and primary languages.
- **URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/github?q=x402`
- **POST Body:** `{"query": "x402", "limit": 8}`

### 5. Live DeFi Chain & Protocol TVL (`GET` / `POST /defi`)
Returns total chain TVL and top DeFi protocols ranked by TVL (including 1-day percentage change) via DefiLlama telemetry.
- **URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/defi?chain=Base`
- **POST Body:** `{"chain": "Base", "limit": 8}`

### 6. Authoritative UTC Clock & Live FX Rates (`GET` / `POST /time-fx`)
Returns exact UTC ISO timestamp, Unix epoch seconds, day of week, and live exchange rates across `USD`, `GBP`, `EUR`, `JPY`, `CAD`, `AUD`, and `CHF`.
- **URL:** `https://drs-agent-web-search.dangerous40-ds.workers.dev/time-fx?base=USD`
- **POST Body:** `{"base": "USD"}`

---

## Part B: On-Chain Base Token Verdict & Crypto Telemetry

### 7. Base Token On-Chain Verdict & AI Roast (`$0.015 USDC`)
Inspects any Base ERC-20 token directly via on-chain smart-contract calls across **Uniswap v3** and **Aerodrome** pools, counts 1-hour swap velocity, computes a `0-100` score and `A-F` grade, writes a 1-sentence Llama 3.3 70B roast, and returns a hosted dark-mode receipt card URL.
- **Endpoint (`GET` or `POST`):** `https://drs-base-token-verdict.dangerous40-ds.workers.dev/verdict?token=DEGEN`
- **Price:** `0.015` USDC (`15000` atomic units)
- **OpenAPI Spec:** `https://drs-base-token-verdict.dangerous40-ds.workers.dev/openapi.json`
- **Free Receipt Viewer (`$0`):** `https://drs-base-token-verdict.dangerous40-ds.workers.dev/receipt?id=<receipt_id>`

### 8. Real-Time Crypto Spot Price Telemetry (`$0.001 USDC`)
Returns current USD spot prices for `BTC`, `ETH`, and `SOL`.
- **Endpoint (`GET`):** `https://vapi-unified-node.dangerous40-ds.workers.dev/price` (also at `/`)

### 9. Live DEX Pool Liquidity & Velocity Telemetry (`$0.001 USDC`)
Returns live DEX pool liquidity depth and velocity telemetry for automated DeFi monitoring agents.
- **Endpoint (`GET`):** `https://vapi-unified-node.dangerous40-ds.workers.dev/liquidity`

### 10. Base Mainnet x402 Settlement & Latency Probe (`$0.001 USDC`)
Verifies end-to-end Base Mainnet x402 v2 settlement and edge latency.
- **Endpoint (`GET`):** `https://vapi-unified-node.dangerous40-ds.workers.dev/health`
