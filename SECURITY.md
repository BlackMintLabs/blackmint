# Security Policy

## Reporting a Vulnerability

At BlackMint, we take security seriously. If you discover a security vulnerability, we appreciate your responsible disclosure and will work with you to resolve it promptly.

**Please do not report security vulnerabilities through public GitHub issues** — this would expose the vulnerability before it's fixed.

Instead, please report vulnerabilities privately using GitHub's built-in security advisory feature:

1. Go to the [Security tab](https://github.com/BlackMintLabs/blackmint/security) of this repository
2. Click **"Report a vulnerability"**
3. Fill in the details — this creates a private report visible only to us, not the public

Include the following in your report:
- A clear description of the vulnerability
- Steps to reproduce the issue
- The potential impact of the vulnerability
- Any suggested fixes (optional)

## What to Expect

- We will acknowledge your report within 48 hours
- We will provide a more detailed response within 7 days
- We will keep you informed of our progress throughout the process
- We will notify you when the vulnerability has been resolved

## Scope

The following are in scope for security reports:
- blackmint.app and all subdomains
- BlackMint API endpoints
- Authentication and wallet connection flows
- On-chain payment verification logic
- API key generation and management

The following are out of scope:
- Third-party services and APIs (Helius, Anthropic, CoinGecko, DexScreener)
- The Solana blockchain itself
- Social engineering attacks
- Denial of service attacks

## Supported Versions

| Version | Supported |
|---------|-----------|
| Latest  | Yes       |
| Older   | No        |

## Security Measures

BlackMint implements the following security practices:
- All wallet authentication uses Sign-In With Solana (SIWS) — we never store or request private keys
- On-chain payment verification with replay protection — each transaction signature can only be used once
- API keys are stored as SHA-256 hashes — plaintext keys are shown only once at creation
- All connections are encrypted via HTTPS/TLS
- No personal data is collected — your wallet address is your identity

## Responsible Disclosure

We follow responsible disclosure principles. We ask that you:
- Give us reasonable time to fix the issue before public disclosure
- Not exploit the vulnerability beyond what is necessary to demonstrate it
- Not access, modify, or delete user data
- Act in good faith throughout the process

We will not pursue legal action against researchers who follow these guidelines.
