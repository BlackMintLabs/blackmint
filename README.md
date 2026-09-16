<div align="center">

<img src="./blackmint-logo.png" width="80" height="80" alt="BlackMint Logo" />

# BlackMint

**Solana Wallet Intelligence for Serious Traders**

[![License](https://img.shields.io/badge/license-MIT-C8FF00?style=flat-square)](LICENSE)
[![Built on Solana](https://img.shields.io/badge/built%20on-Solana-9945FF?style=flat-square&logo=solana)](https://solana.com)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=flat-square&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript)](https://typescriptlang.org)

*See what smart money sees. Act before they move.*

[Report a Bug](https://github.com/BlackMintLabs/blackmint/issues) · [Request a Feature](https://github.com/BlackMintLabs/blackmint/issues)

</div>

---

## What is BlackMint?

BlackMint is a real-time Solana wallet intelligence platform built for traders who want an edge. It gives you deep visibility into on-chain activity — from whale movements to wallet-level risk scoring — all backed by live blockchain data.

**Every feature is free to use.** No sign-ups, no credit cards, no subscription required. Connect your Solana wallet and start in seconds.

---

## Features

### Mint Scan
A live, standalone feed of newly listed Solana tokens, each cross-checked against the on-chain risk profile of the wallet that deployed it — helping you spot likely low-quality launches before you interact with them. Includes real-time price charts, favoriting, and a Simple mode for less experienced traders.

### Whale Tracker
Monitor high-value wallets in real time. Build a watchlist of whale addresses, track their SOL balances, and see recent activity at a glance.

### Risk Score
On-chain heuristic risk assessment for any Solana wallet. BlackMint analyses activity history, transaction failure rates, and holding concentration to generate a 0–100 risk score, with optional AI-generated recommendations explaining the result in plain English.

### Transaction Intelligence
Full enriched transaction history powered by Helius. Filter by swaps, transfers, and failed transactions, with token logos, counterparty addresses, and volumes.

### Wallet Search
Analyse any Solana wallet address instantly. Search, compare, and track wallets with a single click. Recent searches are saved locally for quick access.

### AI Assistant
AI-powered wallet analysis. Ask questions about any wallet and surface insights from on-chain data in plain English.

### REST API
Programmatic access to BlackMint's wallet and market data for developers and quant traders. Generate an API key for free and start making requests immediately — wallet balances, token holdings, transaction history, risk scores, live token charts, market data, and watchlist leaderboards are all available. Higher request-rate tiers are available as a paid upgrade for heavier usage.

### Market Overview
Real-time Solana ecosystem market data — top tokens by market cap, 24H price changes, and volume.

### Wallet Alerts
Real-time Telegram notifications when a monitored wallet makes an on-chain move, with a full alert history and simple wallet-monitoring management.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 16, React, TypeScript, Tailwind CSS |
| Backend | Node.js, Express, TypeScript |
| Database | PostgreSQL |
| Blockchain | Solana Web3.js, Wallet Adapter, SIWS |
| Data | Helius RPC & DAS API, GMGN market data, CoinGecko |
| AI | Anthropic Claude (Haiku) |
| Auth | Sign-In With Solana (JWT) + API key authentication |
| Payments | On-chain SOL payments with replay protection, priced in live USD-equivalent SOL |

---

## Pricing

BlackMint itself is completely free to use — every feature, unlimited. The only thing that's ever paid is **API access**, for developers who need a higher request rate than the free tier provides. Pricing follows a simple weight-based model: every plan gets a request-rate budget, and each API endpoint costs a fixed weight against that budget.

| Plan | Price | Rate Budget |
|---|---|---|
| **Free** | $0 | Weight 5 (~5 requests/sec) |
| **Premium** | $250 / year | Weight 20 (~20 requests/sec) |
| **Pro** | $750 / year | Weight 50 (~50 requests/sec) |

All API payments are on-chain, in SOL, priced live against the current SOL/USD rate at checkout — you always pay the equivalent of the listed USD price, not a fixed SOL amount.

---

## Getting Started

### Prerequisites

- Node.js 18+
- A Solana wallet (Phantom, Solflare, etc.)

### Connect and Go

1. Connect your Solana wallet
2. Sign the authentication message
3. Every feature is unlocked instantly — no plan selection required

### API Access

Generate a free API key from your dashboard to start making requests right away. If you need a higher request rate, upgrade your API plan — payment is confirmed on-chain within seconds.

---

## Architecture

```
blackmint-frontend/     -> Next.js app (Vercel)
blackmint-backend/      -> Express API (Railway)
                        -> PostgreSQL (Railway)
                        -> Helius RPC (Solana data)
                        -> GMGN (market & token data)
                        -> Anthropic API (AI)
```

The frontend communicates with the backend via a REST API. Authentication uses Sign-In With Solana (SIWS) — your wallet signs a message, the backend verifies the signature and issues a JWT. No passwords are ever used or stored. External API requests authenticate with a generated API key instead, rate-limited according to your plan.

API subscription payments are verified on-chain by checking the Solana blockchain for a confirmed SOL transfer to the BlackMint treasury wallet worth at least the plan's listed USD price at the time of payment.

---

## Roadmap

- [x] Wallet overview and SOL balance tracking
- [x] Full transaction history with enriched metadata
- [x] On-chain risk scoring with AI recommendations
- [x] Whale watchlist and tracker
- [x] AI wallet assistant
- [x] On-chain SOL subscription payments, USD-pegged with live conversion
- [x] Telegram bot alerts for monitored wallets
- [x] Mint Scan — standalone new token risk discovery feed with live charts
- [x] Real, working REST API authentication with weight-based rate limiting
- [x] Persistent favorites on Mint Scan
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

Found a bug or have a feature idea? Open an issue directly on this repository — every bug report, feature request, and question is tracked here in the open.

---

## License

This repository (documentation, issue tracking, and support) is provided as-is for transparency and community engagement.

BlackMint's application source code (frontend and backend) is proprietary and not included in this repository. The MIT license badge above applies only to the contents of this repository itself — the README, documentation, and any code samples shown here.

See [LICENSE](LICENSE) for the full text.

---

<div align="center">

Built on Solana

</div>
