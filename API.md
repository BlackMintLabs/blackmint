<div align="center">

<img src="./blackmint-logo.png" width="80" height="80" alt="BlackMint Logo" />

# BlackMint API

**Real-time Solana wallet intelligence and market data, over REST.**

[![License](https://img.shields.io/badge/license-MIT-C8FF00?style=flat-square)](LICENSE)
[![Built on Solana](https://img.shields.io/badge/built%20on-Solana-9945FF?style=flat-square&logo=solana)](https://solana.com)

</div>

---

> Query any Solana wallet's on-chain risk profile, transaction history, and holdings — plus live token discovery, market data, and price charts — with a single API key. Free to start, no signup fee, no credit card. Upgrade only if you need a higher request rate.

---

## Contents

- [Quick Start](#quick-start)
- [Authentication](#authentication)
- [Rate Limits](#rate-limits)
- [Endpoints](#endpoints)
- [Errors](#errors)
- [Notes](#notes)

---

## Quick Start

**1. Get a key** — connect your wallet on BlackMint, sign in, and generate a key from the API tab. It's free, instant, and requires no subscription.

**2. Make a request:**

```bash
curl <your-api-host>/api/wallet/{address}/risk \
  -H "Authorization: Bearer bm_live_your_key_here"
```

**3. Read the response:**

```json
{
  "score": 42,
  "band": "Medium",
  "stats": {
    "txCount": 87,
    "failed": 3,
    "ageDays": 120
  }
}
```

That's it — no OAuth flow, no client registration, no approval wait.

---

## Authentication

Every request needs your key in one of these headers:

| Header | Example |
|---|---|
| `Authorization` | `Bearer bm_live_your_key_here` |
| `X-API-Key` | `bm_live_your_key_here` |

Missing or invalid keys return `401 Unauthorized`.

---

## Rate Limits

BlackMint uses a weight-based system: your plan gives you a total request-weight budget per second, and each endpoint costs a fixed weight against it.

| Plan | Price | Weight Budget | Example |
|---|---|---|---|
| **Free** | $0 | 5 | ~5 req/sec on a weight-1 endpoint |
| **Premium** | $250 / year | 20 | ~10 req/sec on a weight-2 endpoint |
| **Pro** | $750 / year | 50 | ~25 req/sec on a weight-2 endpoint |

**Requests/sec = your plan's weight budget ÷ the endpoint's weight.**

Going over budget returns a `429 Too Many Requests` response, with a `Retry-After` header telling you how long to wait:

```json
{
  "error": "Rate limit exceeded",
  "tier": "free",
  "budget": 5,
  "weight": 2
}
```

Paid plans are billed once a year, on-chain in SOL, computed live against the current SOL/USD rate at checkout — you always pay the listed USD price, never a stale SOL amount.

---

## Endpoints

| Endpoint | Weight | What it returns |
|---|---|---|
| [`GET /wallet/:address/tokens`](#get-walletaddresstokens) | 1 | SPL token holdings and balances |
| [`GET /wallet/:address/balance`](#get-walletaddressbalance) | 1 | Live SOL balance |
| [`GET /wallet/:address/risk`](#get-walletaddressrisk) | 2 | BlackMint AI Risk Score (0–100) |
| [`GET /wallet/:address/transactions`](#get-walletaddresstransactions) | 2 | Enriched transaction history |
| [`GET /wallet/:address/risk-history`](#get-walletaddressrisk-history) | 2 | Stored risk score history |
| [`GET /discover`](#get-discover) | 2 | Live Mint Scan token feed |
| [`GET /discover/chart/:address`](#get-discoverchartaddress) | 2 | Candlestick price chart |
| [`GET /watchlist/leaderboard/:mint`](#get-watchlistleaderboardmint) | 3 | Top holders for a token |
| [`GET /market/prices`](#get-marketprices) | 1 | Live BTC/ETH/SOL/BNB/XRP prices |
| [`GET /market/sentiment`](#get-marketsentiment) | 1 | Fear & Greed index reading |
| [`GET /market/top`](#get-markettop) | 1 | Top-performing Solana tokens |

---

### `GET /wallet/:address/tokens`

SPL token holdings and balances for a wallet.

Request:

```bash
curl <your-api-host>/api/wallet/{address}/tokens \
  -H "Authorization: Bearer bm_live_..."
```

Response:

```json
{
  "address": "...",
  "count": 3,
  "tokens": [
    { "mint": "...", "symbol": "...", "amount": 1000 }
  ]
}
```

---

### `GET /wallet/:address/balance`

Live SOL balance for a wallet.

---

### `GET /wallet/:address/risk`

The BlackMint AI Risk Score for a wallet — built from activity history, transaction failure rate, and portfolio diversification. Never fabricated: if the underlying data source is temporarily unavailable, `score` and `band` return `null` rather than a guessed value.

Request:

```bash
curl <your-api-host>/api/wallet/{address}/risk \
  -H "Authorization: Bearer bm_live_..."
```

Response:

```json
{
  "score": 42,
  "band": "Medium",
  "factors": [
    {
      "name": "Activity History",
      "score": 30,
      "weight": 0.25,
      "detail": "Recent activity spans ~120 days"
    }
  ],
  "stats": {
    "txCount": 87,
    "failed": 3,
    "failedRatio": 0.034,
    "ageDays": 120,
    "distinctTokens": 6,
    "topShare": 0.41
  }
}
```

---

### `GET /wallet/:address/transactions`

Enriched transaction history — swaps, transfers, staking, and failed transactions.

---

### `GET /wallet/:address/risk-history`

Stored history of how a wallet's risk score has changed over time.

---

### `GET /discover`

The live Mint Scan feed — New, Near Migration, and Migrated Solana tokens, each cross-checked against the on-chain risk profile of the wallet that deployed it.

---

### `GET /discover/chart/:address`

Candlestick price data for a token.

**Query params:** `resolution` — `30s` | `1m` | `5m` | `15m` | `1h` | `4h` | `1d` (default `5m`)

Request:

```bash
curl "<your-api-host>/api/discover/chart/{address}?resolution=5m" \
  -H "Authorization: Bearer bm_live_..."
```

Response:

```json
{
  "candles": [
    {
      "time": 1788341130,
      "open": 0.0000334,
      "high": 0.0000335,
      "low": 0.0000327,
      "close": 0.0000327,
      "volume": 25.24
    }
  ],
  "cached": false
}
```

---

### `GET /watchlist/leaderboard/:mint`

Top holders for a given SPL token mint.

---

### `GET /market/prices`

Live prices and 24h change for BTC, ETH, SOL, BNB, and XRP.

Response:

```json
{
  "coins": [
    { "symbol": "SOL", "name": "Solana", "price": 99.31, "change24h": -4.98 }
  ],
  "cached": false
}
```

---

### `GET /market/sentiment`

Current Fear & Greed index reading.

---

### `GET /market/top`

Top-performing Solana tokens right now.

---

## Errors

| Status | Meaning |
|---|---|
| `400` | Invalid request — usually a malformed wallet/token address |
| `401` | Missing or invalid API key |
| `404` | Resource not found |
| `429` | Rate limit exceeded for your plan |
| `502` | An upstream data source (Helius, GMGN, CoinGecko) is temporarily unavailable |

---

## Notes

- Every response is built from live on-chain and market sources — nothing is simulated, cached indefinitely, or estimated.
- Store your API key securely. BlackMint only ever stores a hash of it — the plaintext key is shown once, at creation, and can't be retrieved again.
- Endpoints and response shapes may evolve. Check the [Changelog](CHANGELOG.md) for updates.
- Found a bug or want an endpoint added? [Open an issue](https://github.com/BlackMintLabs/blackmint/issues).
