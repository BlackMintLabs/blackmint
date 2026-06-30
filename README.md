<div align="center">

<img src="https://raw.githubusercontent.com/BlackMintGG/blackmint-frontend/main/public/whale.svg" width="80" height="80" alt="BlackMint Logo" />

# BlackMint

**Solana Wallet Intelligence for Serious Traders**

[![License](https://img.shields.io/badge/license-MIT-C8FF00?style=flat-square)](LICENSE)
[![Built on Solana](https://img.shields.io/badge/built%20on-Solana-9945FF?style=flat-square&logo=solana)](https://solana.com)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=flat-square&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript)](https://typescriptlang.org)

*See what smart money sees. Act before they move.*

[Visit BlackMint](https://blackmint.app) · [Report a Bug](https://github.com/BlackMintGG/blackmint-frontend/issues) · [Request a Feature](https://github.com/BlackMintGG/blackmint-frontend/issues)

</div>

---

## What is BlackMint?

BlackMint is a real-time Solana wallet intelligence platform built for traders who want an edge. It gives you deep visibility into on-chain activity — from whale movements and smart money signals to transaction history and wallet risk profiles — all in one clean, fast interface.

No sign-ups. No credit cards. Connect your Solana wallet and start in seconds. Payments are fully on-chain in SOL.

---

## Features

### 🐳 Whale Tracker
Monitor high-value wallets in real time. Build a watchlist of whale addresses, track their SOL balances, and get alerted when smart money moves. See 24H and 7D balance changes, activity breakdowns, and movement alerts at a glance.

### 🛡️ Risk Score
On-chain heuristic risk assessment for any Solana wallet. BlackMint analyses activity history, transaction failure rates, asset diversification, and behavioural patterns to generate a 0–100 risk score with AI-powered recommendations.

### 📊 Transaction Intelligence
Full enriched transaction history powered by Helius. Filter by swaps, transfers, staking, and failed transactions. See token logos, counterparty addresses, volumes, and fees — with live activity updates and whale alerts.

### 🔍 Wallet Search
Analyse any Solana wallet address instantly. Search, compare, and track wallets with a single click. Recent searches are saved locally for quick access.

### 🤖 AI Assistant
Claude-powered wallet analysis. Ask questions about any wallet, get risk explanations, and surface insights from on-chain data in plain English.

### 🔑 REST API
Programmatic access to BlackMint's wallet data for developers and quant traders. Generate API keys, access wallet balances, token holdings, transaction history, and the top-holder leaderboard for any SPL token.

### 📈 Market Overview
Real-time Solana ecosystem market data — top 100 tokens by market cap, 24H price changes, volume, and Fear & Greed sentiment gauge.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 16, React, TypeScript, Tailwind CSS |
| Backend | Node.js, Express, TypeScript |
| Database | PostgreSQL |
| Blockchain | Solana Web3.js, Wallet Adapter, SIWS |
| Data | Helius RPC & DAS API |
| AI | Anthropic Claude (Haiku) |
| Auth | Sign-In With Solana (JWT) |
| Payments | On-chain SOL payments with replay protection |

---

## Pricing

BlackMint uses fully on-chain SOL payments. No credit cards, no KYC, no subscriptions managed by us — everything is verified directly on the Solana blockchain.

| Plan | Price | Features |
|---|---|---|
| **Free** | $0 | Wallet overview, market data, basic search |
| **Premium** | 0.5 SOL / 30 days | Full transaction history, risk scoring, token analytics |
| **Pro** | 2 SOL / 30 days | Everything in Premium + whale tracking, AI assistant, API access, unlimited watchlists |

---

## Getting Started

### Prerequisites

- Node.js 18+
- A Solana wallet (Phantom, Solflare, etc.)

### Connect and Go

1. Visit [blackmint.app](https://blackmint.app)
2. Click **Connect Wallet**
3. Sign the authentication message
4. Start analysing wallets instantly on the Free plan

### Upgrade

Navigate to **Subscribe** in the dashboard, select your plan, and confirm the SOL payment directly from your wallet. Access is granted on-chain within seconds.

---

## Architecture

```
blackmint-frontend/     → Next.js app (Vercel)
blackmint-backend/      → Express API (Railway)
                        → PostgreSQL (Railway)
                        → Helius RPC (Solana data)
                        → Anthropic API (AI)
```

The frontend communicates with the backend via a REST API. Authentication uses Sign-In With Solana (SIWS) — your wallet signs a message, the backend verifies the signature and issues a JWT. No passwords, no emails required.

Subscription payments are verified on-chain by checking the Solana blockchain for a confirmed SOL transfer to the BlackMint treasury wallet with the correct amount.

---

## Roadmap

- [x] Wallet overview and SOL balance tracking
- [x] Full transaction history with enriched metadata
- [x] On-chain risk scoring
- [x] Whale watchlist and tracker
- [x] AI wallet assistant
- [x] REST API with key management
- [x] On-chain SOL subscription payments
- [ ] Telegram bot alerts for whale movements
- [ ] Risk history page
- [ ] Portfolio tracking across multiple wallets
- [ ] Mobile app

---

## Security

- All payments are verified on-chain with replay protection (each transaction signature can only be used once)
- Wallet authentication uses Sign-In With Solana — we never store private keys
- API keys are stored as SHA-256 hashes — the plaintext key is only shown once at creation
- No personal data is collected — your wallet address is your identity

---

## Contributing

BlackMint is currently in private beta. The repository will be open-sourced following the public launch. Watch this repo to be notified.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">

Built with ⚡ on Solana

[blackmint.app](https://blackmint.app) · [@BlackMintApp](https://twitter.com/BlackMintApp)

</div>
