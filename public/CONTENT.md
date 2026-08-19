# Redbelly DAO Start Here

**Onboarding hub for Redbelly DAO. TASK-17, Redbelly DAO Community Task Board, Cycle 2.**

Read the scam warning first, then work down the page. Every claim in this document is either
verified against official Redbelly documentation or labelled with the source it came from.

---

> ## SCAM WARNING, READ FIRST
>
> ### **Nobody official will ever DM you first.**
>
> **Redbelly staff, moderators, and official support never send the first direct message.
> Any DM offering support, announcing a giveaway, or asking for a seed phrase is a scam.**
>
> Section 01 has the full list of patterns.

---

| | |
|---|---|
| **Live application** | `redbellydaotask17-one.vercel.app` |
| **Repository** | `github.com/poundeater/task17hub` |
| **Mainnet** | Redbelly Network, Chain ID `151` |
| **Testnet** | Redbelly Testnet, Chain ID `153` |
| **Brand kit** | Kinetic Consensus brand kit |
| **Last verified** | `19 AUGUST 2026` |

## Contents

1. [Scam warning](#01-scam-warning)
2. [KYC and eligibility](#02-kyc-and-eligibility)
3. [Network setup](#03-network-setup)
4. [Wallet reads zero](#04-wallet-reads-zero)
5. [Where to buy and trade](#05-where-to-buy-and-trade)
6. [Staking basics](#06-staking-basics)
7. [Testnet faucet](#07-testnet-faucet)

Plus [Cross-links](#cross-links), [Sources and verification](#sources-and-verification),
and [Where the record is thin](#where-the-record-is-thin).

Sections 01 through 07 follow the order of the live board page. Every factual claim carries a
status: official documentation, cross-checked against two or more independent sources,
mod-verified from Discord with no published document, or community-verified. The full list sits
in the verification tables at the end.

**Read first.** Section 01 is the scam warning. Nothing else on this page matters if a seed
phrase is already gone.

**Keep current.** Exchange listings, staking rates, and chain settings expire. Check the
last-verified date above before you rely on them.

---

## 01 Scam warning

**Read this before anything else.**

> ### **Nobody official will ever DM you first.**
>
> **Redbelly staff, moderators, and official support never send the first direct message.
> There are no exceptions to this rule. Any direct message claiming to be from Redbelly staff,
> offering support, or announcing a giveaway is a scam.**

### Common patterns to watch for

- An unsolicited DM offering help with a wallet problem or a KYC issue.
- A giveaway, airdrop, or reward that requires a wallet connection or a seed phrase to claim.
- Anyone asking for your seed phrase or private key, or asking you to verify your wallet
  through a link.
- A support agent who contacts you before you asked anyone for help.
- Any link that arrives by DM, including from an account using the Redbelly name, logo,
  and banner.

Official Redbelly communication happens in public only: this site, the official documentation,
and public Discord channels. If you are not sure whether a message is legitimate, do not click
the link and do not connect your wallet. Ask in a public channel first.

### If you have already shared a seed phrase or connected to a suspicious site

Move your funds to a new wallet now. A seed phrase cannot be revoked or rotated, so the old
wallet stays compromised for as long as it holds anything. Create a fresh wallet, transfer out,
and report the account in a public channel so others see it.

---

## 02 KYC and eligibility

**Required for native RBNT and mainnet. Not required for wrapped RBNT.**

KYC is required for native RBNT and any mainnet activity: transactions, staking, and
governance. It is not required to hold or trade wrapped RBNT on another chain.

Redbelly gates its own Layer 1 behind identity verification through the Redbelly Access portal
at `access.redbelly.network`. Wrapped RBNT on Ethereum or any other chain is a standard ERC-20
with no Redbelly-side identity check.

| | |
|---|---|
| **Wallets per verified identity** | Up to `10 wallets`. One identity covers every wallet you control. |
| **Typical approval time** | `3 to 5 minutes`. Submissions sent for manual review take longer. |

> `MOD-VERIFIED, DISCORD, NO PUBLISHED DOC`
>
> The 10 wallet limit and the 3 to 5 minute approval time. Source: Redbelly Individual
> Onboarding SDK overview, `docs.redbelly.network`, raised in Discord. No published document
> states either figure.

### Regional restrictions

Eighteen jurisdictions are currently restricted from accessing the Redbelly Network platform.

Afghanistan, Central African Republic, Democratic Republic of the Congo, Guinea-Bissau, Iran,
Iraq, Lebanon, Libya, Myanmar, North Korea, Russia, Somalia, South Sudan, Sudan, Syria,
Ukraine, Yemen, Zimbabwe.

Anyone outside this list can proceed with KYC and mainnet access. Anyone inside it cannot,
regardless of which wallet or exchange they use.

> `SOURCE`
>
> Redbelly Network Terms and Conditions, Clause 15,
> `redbelly.network/terms-and-conditions`.

---

## 03 Network setup

**Mainnet is Chain ID 151. Testnet is Chain ID 153.**

No field is shared between the two networks. Chain ID, RPC endpoint, and block explorer are
each unique to their own network. Adding a network by hand works in any wallet that accepts a
custom EVM network.

| Field | MAINNET, real RBNT, real value | TESTNET, free RBNT, no value |
|---|---|---|
| Chain ID | `151` | `153` |
| Currency symbol | `RBNT` | `RBNT` |
| Decimals | `18` | `18` |
| RPC URL | `governors.mainnet.redbelly.network` | `governors.testnet.redbelly.network` |
| Block explorer | `redbelly.routescan.io` | `redbelly.testnet.routescan.io` |

> **Check the chain ID before you sign anything.**
>
> A transaction sent on the wrong network is the most common reason a transfer appears to
> vanish. The funds are not lost. They are on the other chain, and the explorer for that chain
> will show them.

> `SOURCE`
>
> `chainlist.org/chain/151` and `chainlist.org/chain/153`, plus the `ethereum-lists/chains`
> repository, cross-checked against a live call to the testnet RPC endpoint. Two testnet
> explorer URLs are in circulation. This document uses `redbelly.testnet.routescan.io`, the
> more recently updated of the two.

---

## 04 Wallet reads zero

**Almost always wrapped RBNT, not native RBNT.**

A zero balance does not mean lost funds. In almost every case the tokens are on chain and
visible on the explorer, and the wallet is simply not displaying them yet.

Native RBNT is the network's gas token and needs no contract address to display correctly.
Wrapped RBNT does. If a wrapped RBNT balance reads zero, check in this order.

**1. Contract address.** Confirm the wrapped RBNT contract address is added correctly in your
wallet. A missing or wrong contract address is the most common cause of a zero display.

| Network | Wrapped RBNT contract |
|---|---|
| Ethereum | `0xb45ffb51984d626ee758b336c61cf20990c6bf13` |
| Base | `0x020940df9f5e77338a094d55b5b5914122a804a5` |

**2. Try another wallet.** Check the same address in a different wallet extension, for example
Rabby. If the balance appears there, the problem is the first wallet's display, not your funds.

**3. Check the block explorer.** Look the address up directly on Routescan at
`redbelly.routescan.io`. If the balance is there, the funds are safe and the discrepancy is on
the wallet side only.

**4. Check the source transaction.** If the balance is not showing anywhere, including the
explorer, confirm the original transfer or bridge actually executed. That is a different
problem, and the explorer will show which step failed.

> `MOD-VERIFIED, DISCORD, NO PUBLISHED DOC`
>
> This entire explainer. Source: contributor troubleshooting of wrapped RBNT display issues.
> Not published in official Redbelly documentation.

---

## 05 Where to buy and trade

**Four centralized exchanges, decentralized venues on four networks.**

### Centralized exchanges

MEXC, Gate.io, WhiteBit, BYDFi.

### Decentralized exchanges

| Network | Venues |
|---|---|
| Ethereum | 1inch, OKX DEX, Bitget Web3 |
| Base | KyberSwap, 1inch, OKX DEX, Bitget Web3 |
| Solana | Raydium |
| Redbelly native | Reddex |

### Bridges

Lucid Labs Bridge, Reddex Bridge.

> **Native RBNT and wrapped RBNT are separate assets.**
>
> They live on different chains and they are not interchangeable without a bridge. Check which
> one a venue lists before you trade.

> `SOURCE`
>
> Exchange and DEX listings, plus contract addresses, cross-checked against each venue's own
> pages.

---

## 06 Staking basics

**A mainnet action, so it needs KYC like any other native transaction.**

RBNT can be staked to consensus nodes or storage nodes to help secure the network and earn
rewards.

Pools differ by lock period and reward rate. Some carry no lock period. Others lock funds for a
fixed term at a higher rate. Rates and total value locked change, so read the current numbers
on the staking page rather than trusting a snapshot printed in a document.

| | |
|---|---|
| **Staking venue** | `reddex.io/stake` |
| **Node types** | Consensus nodes and storage nodes |
| **KYC** | Required. Staking is a native mainnet transaction. |
| **Network** | Redbelly Network, Chain ID `151` |

> `SOURCE`
>
> Staking mechanism confirmed against the Redbelly Network whitepaper, which covers consensus
> node and storage node staking. Live pool terms from `reddex.io/stake`.

---

## 07 Testnet faucet

**Free testnet RBNT on Chain ID 153.**

The faucet pays `500 RBNT` per claim. That is enough for a large number of deployments and test
transactions, because gas on testnet is effectively zero.

| | |
|---|---|
| **Faucet** | `vine.redbelly.network/rbnt-faucet` |
| **Claim amount** | `500 RBNT` per claim |
| **Powered by** | `FAUCETME` |
| **Network** | Redbelly Testnet, Chain ID `153` |
| **Deployment cost** | Effectively zero gas on testnet |

Testnet RBNT has no value and cannot be bridged to mainnet. It exists so you can deploy and
test without spending anything.

> `SOURCE`
>
> `vine.redbelly.network/rbnt-faucet`, confirmed live.

---

## Cross-links

Every source referenced in this document, in one place.

| | |
|---|---|
| Redbelly docs | `docs.redbelly.network` |
| Access portal | `access.redbelly.network` |
| Terms, Clause 15 | `redbelly.network/terms-and-conditions` |
| Mainnet explorer | `redbelly.routescan.io` |
| Testnet explorer | `redbelly.testnet.routescan.io` |
| Chainlist, mainnet | `chainlist.org/chain/151` |
| Chainlist, testnet | `chainlist.org/chain/153` |
| Faucet | `vine.redbelly.network/rbnt-faucet` |
| Staking | `reddex.io/stake` |
| Brand kit | Kinetic Consensus brand kit |
| Repository | `github.com/poundeater/task17hub` |
| Live application | `redbellydaotask17-one.vercel.app` |

---

## Sources and verification

Every claim in this document, with its status and its source. Anything not listed here is not
asserted as fact.

| Status | Meaning |
|---|---|
| `OFFICIAL DOCS` | Stated in Redbelly documentation, the whitepaper, or the terms. |
| `CROSS-CHECKED` | Confirmed against two or more independent sources. |
| `MOD-VERIFIED` | Raised by a moderator in Discord. No published document. |
| `COMMUNITY` | Community-verified or subject to change. Read it at the source. |

### Confirmed in published sources

| Claim | Status | Source |
|---|---|---|
| Mainnet chain ID 151, RPC endpoint, and block explorer | `CROSS-CHECKED` | `chainlist.org/chain/151` and the `ethereum-lists/chains` repository. |
| Testnet chain ID 153 and RPC endpoint | `CROSS-CHECKED` | `chainlist.org/chain/153`, confirmed against a live call to the testnet RPC endpoint. |
| KYC is required for mainnet and native RBNT | `OFFICIAL DOCS` | `docs.redbelly.network` and the Redbelly Access portal at `access.redbelly.network`. |
| Eighteen restricted jurisdictions | `OFFICIAL DOCS` | Redbelly Network Terms and Conditions, Clause 15, `redbelly.network/terms-and-conditions`. |
| Wrapped RBNT contract addresses on Ethereum and Base | `CROSS-CHECKED` | Venue listings checked against the contract pages on each network's block explorer. |
| Staking to consensus nodes and storage nodes | `OFFICIAL DOCS` | Redbelly Network whitepaper. |
| Faucet pays 500 RBNT per claim | `CROSS-CHECKED` | `vine.redbelly.network/rbnt-faucet`, confirmed live. |

### Where the record is thin

Five claims in this document have no published document behind them. They are included because
they are useful and because leaving them out would be less honest than labelling them. Treat
each one as accurate at the time of writing, not as documented fact.

| Claim | Status | Source |
|---|---|---|
| Testnet block explorer URL | `COMMUNITY` | Two testnet explorer URLs are in circulation. This document uses `redbelly.testnet.routescan.io`, the more recently updated of the two. |
| Up to 10 wallets per verified identity | `MOD-VERIFIED` | Redbelly Individual Onboarding SDK overview, raised in Discord. No published document states the limit. |
| Approval takes 3 to 5 minutes | `MOD-VERIFIED` | Discord. No published document states the timing. Submissions sent for manual review take longer. |
| Zero balance troubleshooting order | `COMMUNITY` | Contributor troubleshooting of wrapped RBNT display issues. Not published in official Redbelly documentation. |
| Live staking pool terms, lock periods, and rates | `COMMUNITY` | `reddex.io/stake`. These change over time, so read them at the source. |

**If you find a published source for any of these, it belongs in this table.** Open an issue on
`github.com/poundeater/task17hub` with the link and the claim it settles. The table is the part
of this document most likely to go stale, so it is the part most worth correcting.

---

## Colophon

Produced for the Redbelly DAO Community Task Board, Cycle 2, TASK-17. Set in Be Vietnam Pro,
with JetBrains Mono reserved for machine-generated values: chain IDs, contract addresses, RPC
endpoints, task IDs, and status labels. Colour, radius, and spacing values are the Kinetic
Consensus tokens. Where this document and the brand kit disagree, the brand kit is right.

Repository `github.com/poundeater/task17hub`. Live application
`redbellydaotask17-one.vercel.app`. Last verified `19 AUGUST 2026`.

Contributed by `poundeater / task17hub`, the same attribution carried in the footer of every
page of the PDF and Word editions.

### Reproducing the deliverables

```
python3 build_task17.py      # writes Redbelly-DAO-Start-Here.pdf,  12 pages
python3 build_docx.py        # writes Redbelly-DAO-Start-Here.docx, 12 pages

python3 verify_task17.py     # 13 checks on the PDF
python3 verify_docx.py       # 13 checks on the Word file
python3 verify_docs.py       # 10 checks on this file and LOVABLE-PROMPT.md
```

Each verifier exits non-zero on any failure, so the set can gate a commit. The three of them
import one shared list of tokens, machine values, restricted jurisdictions, and trading venues
from `verify_task17.py`. That is deliberate: it means no deliverable can drift from the others
without a verifier failing, and correcting a fact is a one-line edit in one file rather than a
hunt through four.

`verify_task17.py` reads the rendered PDF. It checks page geometry and metadata, rejects blank
and orphan pages, bans en dashes, em dashes, curly quotes and emoji from the text layer,
confirms every embedded typeface is a brand face, pulls every fill colour out of the content
streams and confirms each one is a Kinetic Consensus token, measures eleven text pairings
against WCAG AA, and asserts that all nineteen machine values, all eighteen restricted
jurisdictions, and all six venues survive the build unaltered.

`verify_docx.py` reads the OOXML instead, because a Word file has failure modes a PDF does not:
a colour hidden in a shading attribute, a typeface that only appears in a style definition, a
run that Word will silently render in Calibri because nobody set the high-ANSI font name. It
also resolves the background behind every inked run by walking up the XML to the nearest cell or
paragraph shading, then measures that pairing against WCAG AA at the run's own size and weight.
That is 281 pairings, and it is how the one real contrast defect in this project was found.

`verify_docs.py` covers this file and the Lovable prompt. It requires both to be pure ASCII,
which is a stronger claim than banning the specific characters the brand rules name and easier
to trust. It holds the prompt to an exact two-way match with the palette, so the prompt can
neither invent a colour nor quietly drop one of the seventeen tokens, and it confirms every
in-page link in this document resolves to a real heading.

### The one place this project argues with itself

Brand red `#EF5350` measures 3.49:1 against white and 4.48:1 against the container fill. Both
are under the 4.5:1 that WCAG AA requires for normal text. The kit ships no darkened red, and
inventing one would be a brand-kit violation of a worse kind than the one it fixed. So brand red
is used here as a fill, a border, and a rule colour, and never as small text. Small accents run
in `#ffb3ae` on dark surfaces, which measures 10.53:1, and in `#16202A` on brand fills, which
measures 4.73:1. White on brand red appears in exactly one place, the scam warning headline at
16pt bold, where the 3:1 large-text threshold applies and is met.

This is written down rather than quietly handled because a future contributor will otherwise
read the token comment as an oversight and put red body text back.
