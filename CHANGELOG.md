# Changelog

All notable changes to BlackMint are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]

### Planned
- Telegram bot alerts for whale movements
- Risk history page
- Portfolio tracking across multiple wallets
- Mobile app

---

## [1.0.0] — 2026

### Added
- 🚀 Initial public launch of BlackMint
- Wallet overview dashboard with SOL balance, USD value, token count, and transaction count
- Full enriched transaction history powered by Helius — swaps, transfers, staking, failed transactions
- On-chain risk scoring (0–100) with four heuristic factors: Activity History, Activity Level, Failed Transactions, Diversification
- AI-powered risk recommendations via Anthropic Claude
- Risk score history and trend tracking
- Whale Tracker — watchlist of high-value wallets with balance tracking, 24H/7D change indicators, and activity breakdown
- Token holder leaderboard for any SPL token via Helius DAS API
- AI Assistant — persistent chat powered by Claude with full conversation history
- Wallet search with recent search history and DiceBear avatar identicons
- Market Overview — top 100 Solana tokens with price, market cap, volume, and 24H change
- Fear & Greed sentiment gauge
- Token allocation donut chart
- REST API with key generation, management, and revocation
- Sign-In With Solana (SIWS) authentication
- On-chain SOL subscription payments with replay protection
- Free, Premium, and Pro subscription tiers
- Subscription management page with downgrade, cancel, and resume flows
- Sidebar navigation with tier-aware upgrade prompts
- Landing page with hero, features, pricing, and CTA sections

### Security
- API keys stored as SHA-256 hashes
- On-chain payment verification with transaction signature replay protection
- HTTPS enforced across all endpoints
- Dev backdoor route removed before production launch

---

## [0.9.0] — 2025

### Added
- Beta version of BlackMint
- Core wallet analysis features
- Initial subscription payment flow
- Whale tracking watchlist
- AI assistant integration

---

*BlackMint is built on Solana. All payments are on-chain and fully transparent.*
