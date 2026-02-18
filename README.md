<p align="center">
  <img src="https://grokandmon.com/assets/growring-banner.png" alt="GanjaMon GrowRing" width="800"/>
</p>

<h1 align="center">GanjaMon GrowRing</h1>

<p align="center">
  <b>Autonomous AI agent that grows real cannabis, captures daily webcam photos, generates AI art, and mints NFTs on Monad — with all sensor data permanently recorded on-chain.</b>
</p>

<p align="center">
  <a href="https://monadexplorer.com/address/0x1e4343bAB5D0bc47A5eF83B90808B0dB64E9E43b"><img src="https://img.shields.io/badge/Monad-Deployed-blueviolet?style=for-the-badge&logo=ethereum" alt="Monad Deployed"/></a>
  <a href="https://8004scan.io/agents/monad/4"><img src="https://img.shields.io/badge/ERC--8004-Agent%20%234-green?style=for-the-badge" alt="ERC-8004 Agent #4"/></a>
  <a href="https://grokandmon.com/growring"><img src="https://img.shields.io/badge/GrowRing-Gallery-orange?style=for-the-badge" alt="Gallery"/></a>
  <a href="https://grokandmon.com/dashboard/grow"><img src="https://img.shields.io/badge/Live-Dashboard-blue?style=for-the-badge" alt="Dashboard"/></a>
</p>

<p align="center">
  <a href="https://monskills.pages.dev"><img src="https://img.shields.io/badge/Mon%20Skills-17%20Skills-9cf?style=flat-square" alt="Mon Skills"/></a>
  <a href="https://github.com/How1337ItIs/sol-cannabis"><img src="https://img.shields.io/badge/GitHub-sol--cannabis-black?style=flat-square&logo=github" alt="GitHub"/></a>
  <img src="https://img.shields.io/badge/Solidity-0.8.24-363636?style=flat-square&logo=solidity" alt="Solidity"/>
  <img src="https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python" alt="Python"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="MIT"/>
</p>

---

## What Is This?

A real cannabis plant (**Granddaddy Purple Runtz**) is being grown autonomously by an AI agent running on a Chromebook. Every day, the agent captures a webcam photo of the plant, transforms it into AI-generated art using one of 7 rotating styles, uploads to IPFS, and mints a **GrowRing NFT on Monad** — with all environmental sensor data permanently recorded on-chain.

No human touches the grow decisions. No human triggers the mints. The AI runs the entire pipeline.

> **This is not a simulation.** There is a live plant under grow lights in California right now, and an AI is keeping it alive.

---

## Daily Mint Pipeline

```
                    Every Day @ 11:30 AM PST
                              |
                              v
              +-------------------------------+
              |     Chromebook Server          |
              |   (Ubuntu + Python FastAPI)    |
              +-------------------------------+
                              |
          +-------------------+-------------------+
          |                   |                   |
          v                   v                   v
   +-----------+      +-------------+     +-------------+
   |  Sensors  |      |   Webcam    |     |  Grok AI    |
   | Govee     |      | Logitech    |     | (xAI)       |
   | Ecowitt   |      | C270        |     | Decisions   |
   | Kasa      |      +------+------+     +-------------+
   +-----------+             |
          |                  v
          |         +------------------+
          |         | Gemini 3 Pro     |
          |         | AI Art Gen       |
          |         | (7 styles rotate)|
          |         +--------+---------+
          |                  |
          v                  v
   +-----------+     +--------------+
   | GrowOracle|     | Pinata v2    |
   | On-Chain  |     | IPFS Upload  |
   | Ring Buf  |     +------+-------+
   | (4320 pts)|            |
   +-----+-----+            |
         |                  v
         |         +------------------+
         +-------->| GrowRing.sol     |
                   | mintDaily()      |
                   | ERC-721 on Monad |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   | GrowAuction.sol  |
                   | Auto-list NFT   |
                   +------------------+
```

**7 Rotating Art Styles:** Watercolor Botanical | Cyberpunk Neon | Ukiyo-e Woodblock | Art Nouveau | Pixel Art | Psychedelic Blacklight | Scientific Illustration

---

## Deployed Contracts (Monad)

| Contract | Address | Purpose |
|----------|---------|---------|
| **GrowRing** | [`0x1e4343bAB5D0bc47A5eF83B90808B0dB64E9E43b`](https://monadexplorer.com/address/0x1e4343bAB5D0bc47A5eF83B90808B0dB64E9E43b) | ERC-721 daily NFT collection |
| **GrowOracle** | [`0xc532820dE55363633263f6a95Fa0762eD86E8425`](https://monadexplorer.com/address/0xc532820dE55363633263f6a95Fa0762eD86E8425) | On-chain sensor ring buffer (90 days) |
| **GrowAuction** | [`0xc07cA3A855b9623Db3aA733b86DAF2fa8EA9A5A4`](https://monadexplorer.com/address/0xc07cA3A855b9623Db3aA733b86DAF2fa8EA9A5A4) | Automated NFT listing & sales |

All contracts deployed and verified on Monad Explorer. Built with Foundry + OpenZeppelin.

---

## Architecture

```
+------------------------------------------------------------------+
|                        GanjaMon Agent                             |
|                                                                   |
|  +------------------+  +------------------+  +-----------------+  |
|  |  OpenClaw        |  |  Grok AI Brain   |  |  Trading Agent  |  |
|  |  Orchestrator    |  |  (xAI)           |  |  (GanjaMon)     |  |
|  |  14+ Skills      |  |  14 Grow Tools   |  |  Multi-chain    |  |
|  |  Cron Jobs       |  |  Vision Analysis |  |  Alpha Hunting  |  |
|  +--------+---------+  +--------+---------+  +-----------------+  |
|           |                      |                                |
|  +--------v----------------------v---------+                      |
|  |         FastAPI HAL (Port 8000)         |                      |
|  |  82+ Endpoints | WebSocket | Dashboard  |                      |
|  +--------+-------------------+------------+                      |
|           |                   |                                   |
+------------------------------------------------------------------+
            |                   |
   +--------v------+   +-------v--------+
   |   IoT Sensors  |   |    Monad       |
   | Govee | Ecowitt|   | GrowRing NFT   |
   | Kasa  | Webcam |   | GrowOracle     |
   +----------------+   | ERC-8004 Rep   |
                         | x402 Payments  |
                         +----------------+
```

### Key Components

| Layer | Tech | What It Does |
|-------|------|-------------|
| **AI Brain** | Grok (xAI) + Gemini 3 Pro | Autonomous grow decisions + AI art generation |
| **Orchestrator** | OpenClaw Framework | 14+ custom skills, cron scheduling, multi-channel |
| **Hardware** | Govee, Ecowitt, Kasa, Logitech C270 | Temp, humidity, VPD, soil moisture, CO2, webcam |
| **Server** | Python FastAPI on Chromebook | 82+ REST endpoints, WebSocket dashboard |
| **Blockchain** | Solidity 0.8.24 / Foundry | GrowRing NFT + Oracle + Auction on Monad |
| **Identity** | ERC-8004 Agent #4 | On-chain reputation, trust score ~82 |
| **Payments** | x402 (EIP-3009) | Agent-to-agent micropayments |
| **Monitoring** | QuickNode Monad Streams | Real-time on-chain event tracking |
| **Skills** | Mon Skills (17 skill files) | Monad-centric AI capabilities |
| **Storage** | Pinata v2 IPFS | Decentralized art + metadata storage |

---

## On-Chain Grow Oracle

The **GrowOracle** contract stores environmental sensor readings in a circular ring buffer:

- **4,320 data slots** = 90 days of twice-daily readings
- Temperature, humidity, VPD, soil moisture, CO2, light PPFD
- Immutable on-chain grow journal — verifiable cultivation history
- Any contract or dApp can read the oracle for grow analytics

```solidity
struct SensorReading {
    uint32 timestamp;
    int16  temperature;    // x100 (e.g., 2450 = 24.50C)
    uint16 humidity;       // x100
    uint16 vpd;            // x1000
    uint16 soilMoisture;   // x100
    uint16 co2;            // ppm
    uint16 lightPpfd;      // umol/m2/s
}
```

Monad's parallel EVM execution and low gas costs make it uniquely feasible to store this volume of data on-chain. On Ethereum mainnet, this would cost thousands of dollars per month.

---

## Why Monad?

| Feature | Why It Matters for GrowRing |
|---------|---------------------------|
| **Parallel EVM** | Daily sensor writes + NFT mints + oracle updates execute efficiently |
| **Low Gas** | Storing full grow journals on-chain is economically viable |
| **Speed** | Sub-second finality for real-time sensor data recording |
| **ERC-8004** | Native agent identity standard — GanjaMon is Agent #4 |
| **Growing DeFi** | Future $MON token integration for grow-backed value |
| **Community** | Active builder ecosystem for novel use cases |

---

## Mon Skills

**17 Monad-centric AI skill files** published at [monskills.pages.dev](https://monskills.pages.dev) — reusable by any AI agent building on Monad:

- Monad RPC interaction, contract deployment, token operations
- QuickNode Streams integration for real-time monitoring
- NFT minting pipelines, IPFS metadata standards
- DeFi integration patterns (Bean, Kuru, Curvance)
- ERC-8004 agent registration and reputation

---

## ERC-8004 Agent Identity

GanjaMon is **Agent #4** on the Monad ERC-8004 registry:

- **Trust Score:** ~82.34
- **On-chain signals:** 10 reputation data points published every 4 hours
- **Verifiable identity:** Cryptographic proof of agent capabilities
- **Registry:** [8004scan.io/agents/monad/4](https://8004scan.io/agents/monad/4)

---

## Live Links

| Link | Description |
|------|-------------|
| [GrowRing Gallery](https://grokandmon.com/growring) | Browse all minted GrowRing NFTs with AI art |
| [Live Dashboard](https://grokandmon.com/dashboard/grow) | Real-time sensor data, AI decisions, plant status |
| [Mon Skills](https://monskills.pages.dev) | 17 Monad AI skill files for builders |
| [8004scan Agent #4](https://8004scan.io/agents/monad/4) | ERC-8004 agent profile and trust score |
| [Monad Explorer](https://monadexplorer.com/address/0x1e4343bAB5D0bc47A5eF83B90808B0dB64E9E43b) | GrowRing contract on-chain |
| [GitHub](https://github.com/How1337ItIs/sol-cannabis) | Full source code |

---

## The Plant

| Detail | Value |
|--------|-------|
| **Strain** | Granddaddy Purple Runtz (GDP x Runtz) |
| **Stage** | Vegetative (Feb 2026) |
| **Expected Harvest** | Late April / Early May 2026 |
| **Legal Status** | California Prop 64 (personal cultivation, 6 plants max) |
| **AI Agent** | Grok (xAI) — zero human grow decisions |

The NFT collection will span the full lifecycle: seedling through harvest. Each day's art style and sensor data creates a unique, unrepeatable artifact of that moment in the plant's life.

---

## Tech Stack

```
Blockchain:     Solidity 0.8.24 | OpenZeppelin | Foundry
AI:             Grok (xAI) | Gemini 3 Pro | OpenClaw Framework
Backend:        Python 3.11 | FastAPI | asyncio
Hardware:       Govee H5075 | Ecowitt GW2000 | Kasa KP115 | Logitech C270
Storage:        Pinata v2 IPFS | SQLite
Identity:       ERC-8004 on Monad | 8004scan
Payments:       x402 micropayments (EIP-3009)
Monitoring:     QuickNode Monad Streams
Infrastructure: Cloudflare Workers/Pages | systemd | Chromebook server
```

---

## Getting Started

```bash
# Clone
git clone https://github.com/How1337ItIs/sol-cannabis.git
cd sol-cannabis

# Install
python3 -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env  # Add your API keys

# Run the full agent
python run.py all

# Or run components individually
python run.py server        # FastAPI HAL on :8000
python run.py orchestrator  # Sensor polling + AI decisions

# Deploy contracts (Foundry)
cd contracts/grow
forge build
forge script script/Deploy.s.sol --rpc-url $MONAD_RPC --broadcast
```

---

## Team

**Solo builder** assisted by autonomous AI agents:

| Agent | Role |
|-------|------|
| **Claude Code** | Primary development, architecture, deployment |
| **OpenClaw** | AI orchestration, cron scheduling, multi-channel |
| **Grok (xAI)** | Autonomous cultivation decisions, plant health |
| **Gemini 3 Pro** | Daily AI art generation (7 rotating styles) |

---

## What Makes This Different

Most hackathon projects are demos. **This one has a living plant depending on it.**

- The AI agent has been making real cultivation decisions for weeks
- Sensor data is streaming 24/7 from real hardware
- NFTs are being minted daily with actual plant photos transformed into art
- On-chain oracle contains verifiable environmental history
- If the agent fails, the plant suffers — real stakes, real accountability

**GrowRing is not a concept. It is running right now.**

---

<p align="center">
  <i>Built with soil, sensors, and Solidity for Monad Blitz Denver 2026</i>
</p>
