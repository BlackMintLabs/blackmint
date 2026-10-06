# Privacy Policy

**Effective Date:** July 2026
**Last Updated:** October 2026

## 1. Introduction

BlackMint ("the platform"), is committed to protecting your privacy. This Privacy Policy explains what data we collect, how we use it, and your rights regarding that data. By using the Platform, you agree to the practices described in this policy.

---

## 2. What Data We Collect

BlackMint collects minimal data necessary to operate the Platform:

**Wallet Address**
When you connect your Solana wallet and sign in, we store your wallet address. This is your identity on the Platform — we do not collect your name, email address, or any other personally identifiable information.

**Subscription Data**
If you upgrade your API access, we store your subscription tier, start date, and expiry date. Payment is verified on-chain via transaction signature — we do not store payment card details, bank details, or any financial information.

**Usage Data**
We store data you actively create on the Platform, including:
- Wallet addresses you add to your watchlist
- Wallet monitors you set up for Telegram alerts
- Risk scores generated for wallets you analyse
- API keys you generate (stored as cryptographic hashes only)
- AI conversation history (stored to provide conversation continuity)
- Search history (stored locally in your browser)

**Telegram Data**
If you connect your Telegram account for alerts, we store your Telegram chat ID and username to deliver notifications. We do not store the content of messages sent via Telegram.

**Technical Data**
Standard server logs including request timestamps, IP addresses, and error messages are collected for security and performance monitoring. These are retained for a limited period and are not used for profiling or marketing.

---

## 3. How We Use Your Data

We use the data we collect solely to:

- Authenticate your wallet and maintain your session
- Deliver the Platform's features — transaction history, risk scoring, whale tracking, alerts, and the AI Assistant are available to every connected wallet at no charge
- Verify API subscription payments on-chain, for users who choose to upgrade their API rate limits
- Send Telegram alerts for wallets you have chosen to monitor
- Improve the reliability and performance of the Platform
- Comply with applicable legal obligations

We do not sell, rent, or share your data with third parties for marketing purposes.

---

## 4. Third-Party Services

BlackMint uses the following third-party services to operate the Platform. Each processes data according to their own privacy policies:

- **Helius** — Solana blockchain data and RPC. Wallet addresses and transaction data are sent to Helius to retrieve on-chain information.
- **Anthropic** — AI-powered risk recommendations and the AI Assistant. Wallet analysis context is sent to Anthropic's API to generate insights.
- **CoinGecko** — Market price and token data. No personal data is sent to CoinGecko.
- **alternative.me** — Fear and Greed market sentiment data. No personal data is sent to alternative.me.
- **Vercel** — Frontend hosting. Standard web request logs may be collected by Vercel.
- **Railway** — Backend infrastructure hosting. Server logs are retained by Railway according to their data retention policy.

---

## 5. Data Retention

We retain your data for as long as your account is active. If you stop using the Platform, your data remains stored unless you request deletion. We will delete your account data within 30 days of a verified deletion request submitted via our GitHub repository.

Blockchain transaction data (payment signatures used to verify subscriptions) is public on the Solana blockchain and cannot be deleted, as it is stored by the decentralised network.

---

## 6. Security

We implement industry-standard security measures including:

- HTTPS encryption for all data in transit
- API keys stored as SHA-256 hashes — plaintext keys are never stored
- Wallet authentication via cryptographic signature verification — we never handle private keys
- On-chain payment verification with replay protection

No system is 100% secure. You are responsible for protecting access to your wallet and any API keys you generate.

---

## 7. Your Rights

Depending on your jurisdiction, you may have the right to:

- **Access** the data we hold about you
- **Correct** inaccurate data
- **Delete** your account and associated data
- **Object** to certain types of processing
- **Portability** of your data in a machine-readable format

To exercise any of these rights, please open an issue on our GitHub repository at **github.com/BlackMintLabs/blackmint**.

---

## 8. Cookies and Local Storage

BlackMint uses browser local storage to store your authentication token and recent search history. This data is stored entirely on your device and is not transmitted to our servers except as part of authenticated API requests. We do not use tracking cookies or advertising cookies.

---

## 9. Children's Privacy

The Platform is not intended for users under the age of 18. We do not knowingly collect data from minors. If you believe a minor has provided data to the Platform, please contact us via GitHub.

---

## 10. Changes to This Policy

We may update this Privacy Policy from time to time. When we do, we will update the "Last Updated" date at the top of this page. Continued use of the Platform after changes are posted constitutes your acceptance of the updated policy. For significant changes, we will post a notice on our GitHub repository.

---

## 11. Contact

For any privacy-related questions, requests, or concerns, please open an issue on our GitHub repository at **github.com/BlackMintLabs/blackmint**.

---

*BlackMint is a blockchain intelligence platform. We collect the minimum data necessary to deliver our service and never sell your information.*
