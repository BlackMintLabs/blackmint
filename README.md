<div align="center">

<img src="./blackmint-logo.png" width="80" height="80" alt="BlackMint Logo" />

# BlackMint

**Solana Wallet Intelligence for Serious Traders**

[![License](https://img.shields.io/badge/license-MIT-C8FF00?style=flat-square)](LICENSE)
[![Built on Solana](https://img.shields.io/badge/built%20on-Solana-9945FF?style=flat-square&logo=solana)](https://solana.com)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=flat-square&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript)](https://typescriptlang.org)

*See what smart money sees. Act before they move.*

[Visit BlackMint](https://blackmint.app) · [Report a Bug](https://github.com/BlackMintLabs/blackmint/issues) · [Request a Feature](https://github.com/BlackMintLabs/blackmint/issues)

</div>

---

## What is BlackMint?

BlackMint is a real-time Solana wallet intelligence platform built for traders who want an edge. It gives you deep visibility into on-chain activity — from whale movements to wallet-level risk scoring — all backed by live blockchain data.

No sign-ups. No credit cards. Connect your Solana wallet and start in seconds. Payments are fully on-chain in SOL.

---

## Features

### Whale Tracker
Monitor high-value wallets in real time. Build a watchlist of whale addresses, track their SOL balances, and see recent activity at a glance.

### Risk Score
On-chain heuristic risk assessment for any Solana wallet. BlackMint analyses activity history, transaction failure rates, and holding concentration to generate a 0–100 risk score, with optional AI-generated recommendations explaining the result in plain English.

### Discover
A live feed of newly listed Solana tokens, each cross-checked against the on-chain risk profile of the wallet that deployed it — helping you spot likely low-quality launches before you interact with them.

### Transaction Intelligence
Full enriched transaction history powered by Helius. Filter by swaps, transfers, and failed transactions, with token logos, counterparty addresses, and volumes.

### Wallet Search
Analyse any Solana wallet address instantly. Search, compare, and track wallets with a single click. Recent searches are saved locally for quick access.

### AI Assistant
AI-powered wallet analysis. Ask questions about any wallet and surface insights from on-chain data in plain English. Available on the Pro plan, with a daily message limit.

### REST API
Programmatic access to BlackMint's wallet data for developers and quant traders. Generate API keys, and access wallet balances, token holdings, transaction history, risk scores, and watchlist data for any address.

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
| **Premium** | 0.5 SOL / 30 days | Full transaction history, risk scoring with AI recommendations, Discover feed |
| **Pro** | 2 SOL / 30 days | Everything in Premium, plus whale tracking, AI Assistant, Telegram alerts, and full API access |

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
blackmint-frontend/     -> Next.js app (Vercel)
blackmint-backend/      -> Express API (Railway)
                        -> PostgreSQL (Railway)
                        -> Helius RPC (Solana data)
                        -> Anthropic API (AI)
```

The frontend communicates with the backend via a REST API. Authentication uses Sign-In With Solana (SIWS) — your wallet signs a message, the backend verifies the signature and issues a JWT. No passwords are ever used or stored.

Subscription payments are verified on-chain by checking the Solana blockchain for a confirmed SOL transfer to the BlackMint treasury wallet with the correct amount.

---

## Roadmap

- [x] Wallet overview and SOL balance tracking
- [x] Full transaction history with enriched metadata
- [x] On-chain risk scoring with AI recommendations
- [x] Whale watchlist and tracker
- [x] AI wallet assistant
- [x] REST API with key management
- [x] On-chain SOL subscription payments
- [x] Telegram bot alerts for monitored wallets
- [x] New token risk discovery feed
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

Found a bug or have a feature idea? Open an issue directly on this repository — every bug report, feature request, and question is tracked here in the open. See our [Contact page](https://blackmint.app/contact) for the fastest way to file one.

---

## License

This repository (documentation, issue tracking, and support) is provided as-is for transparency and community engagement.

BlackMint's application source code (frontend and backend) is proprietary and not included in this repository. The MIT license badge above applies only to the contents of this repository itself — the README, documentation, and any code samples shown here.

See [LICENSE](LICENSE) for the full text.

---

<div align="center">

Built on Solana

[blackmint.app](https://blackmint.app) · [@BlackMintApp](https://twitter.com/BlackMintApp)

</div>
