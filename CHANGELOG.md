# Changelog
All notable changes to BlackMint are documented here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]
### Planned
- Portfolio tracking across multiple wallets
- Mobile app

---

## [1.2.0] — 2026
### Changed
- **BlackMint is now free to use** — every feature (Mint Scan, Risk Score, Whale Tracker, AI Assistant, Alerts, Favorites) is available to any connected wallet, no subscription required
- Renamed "Discover" to **Mint Scan**, now its own standalone section with a dedicated navigation bar, live-updating token feed, and real-time price charts
- Subscription tiers now apply to **API access only** — the app itself has no paywall
- API pricing rebuilt around a GMGN-style weight-based rate limit system: Free (weight 5), Premium (weight 20), Pro (weight 50)
- Subscription pricing is now USD-pegged ($250/year Premium, $750/year Pro), with the exact SOL amount computed live from the current SOL/USD price at checkout rather than a fixed SOL amount

### Added
- Real REST API authentication — API keys can now actually authenticate external requests
- Weight-based rate limiting per API tier
- Expanded public API surface: wallet balance, wallet risk history, market prices/sentiment/top movers, and live token charts, alongside the existing wallet risk, transactions, and token holdings endpoints
- Persistent Favorites on Mint Scan, synced to your account instead of resetting each session
- Wallet-level risk score caching to reduce redundant lookups on repeat deployer wallets
- Live-updating token charts, with automatic fallback to a shorter timeframe when a longer one doesn't have enough data yet

### Fixed
- Multiple Mint Scan chart reliability and scaling issues
- Wallet session no longer clears unexpectedly on page refresh

### Removed
- Pricing section removed from the landing page, reflecting BlackMint's move to free-to-use

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
- API key generation and management
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
