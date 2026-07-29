# Changelog
All notable changes to BlackMint are documented here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]
### Planned
- Portfolio tracking across multiple wallets
- Mobile app

---

## [1.1.0] — 2026
### Added
- Discover — live feed of newly listed Solana tokens, each cross-checked against the on-chain risk profile of its deployer wallet
- Telegram wallet alerts — link your account via a one-time code, monitor wallets, and receive instant notifications on-chain activity, with full alert history
- Risk history page — full stored risk score history for any wallet
- Tiered daily usage limits on AI-powered features (AI Assistant, risk recommendations), scaled by subscription tier
- Redesigned Alerts, API documentation, and subscription management pages

---

## [1.0.0] — 2026
### Added
- Initial public launch of BlackMint
- Wallet overview dashboard with SOL balance, USD value, token count, and transaction count
- Full enriched transaction history powered by Helius — swaps, transfers, staking, and failed transactions
- On-chain risk scoring (0–100) with four heuristic factors: Activity History, Activity Level, Failed Transactions, and Diversification
- AI-powered risk recommendations via Anthropic Claude
- Risk score trend tracking
- Whale Tracker — watchlist of high-value wallets with balance tracking, 24H/7D change indicators, and whale activity breakdown
- Token holder leaderboard for any SPL token
- AI Assistant — persistent chat with full conversation history
- Wallet search with recent search history
- Market Overview — top 100 Solana tokens with price, market cap, volume, and 24H change
- Fear and Greed sentiment gauge
- Token allocation chart
- REST API with key generation, management, and revocation
- Sign-In With Solana (SIWS) authentication
- On-chain SOL subscription payments with replay protection
- Free, Premium, and Pro subscription tiers
- Subscription management with downgrade, cancel, and resume flows
- Landing page with hero, features, pricing, and CTA sections

### Security
- API keys stored as SHA-256 hashes
- On-chain payment verification with transaction signature replay protection
- HTTPS enforced across all endpoints
- Production hardened before launch

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
