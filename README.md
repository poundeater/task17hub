# TASK-17: Start Here Onboarding Hub

Redbelly DAO Community Task Board submission. A single canonical onboarding page for new users, covering the seven questions moderators answer most often in Discord.

**Live site:** https://redbellydaotask17-one.vercel.app/

## What this is

Moderators paste the same answers on repeat: KYC, network setup, a wallet showing a zero balance, where to buy or trade, staking basics, scam warnings, and the testnet faucet. This page puts all seven in one place, with a design pass, so a moderator can paste one link instead of retyping the same explanation.

## Sections

01. Scam warning, placed first so it is never missed
02. KYC, native mainnet activity versus wrapped tokens, plus the eighteen restricted jurisdictions
03. Network setup, Mainnet Chain ID 151 and Testnet Chain ID 153, with one-click add to wallet
04. Wallet shows a zero balance, why it happens and how to confirm funds are safe
05. Where to buy and trade, centralized exchanges, DEXs by chain, and bridges
06. Staking basics, consensus and storage node staking through Reddex
07. Testnet faucet signpost, claim link, amount, and typical deployment cost

## Content documents

The full written content behind the site, source-checked and ready for reference:

- [View full PDF](https://cdn.jsdelivr.net/gh/poundeater/task17hub@main/public/TASK-17-content-draft.pdf)
- [View full DOCX](https://docs.google.com/gview?url=https://raw.githubusercontent.com/poundeater/task17hub/main/public/TASK-17-content-draft.docx&embedded=true)

Both are also linked from the footer of the live site.

## Sourcing

Every fact on the page is either cited to an official source or marked community-verified.

- Cited: docs.redbelly.network, the Redbelly Individual Onboarding SDK overview, the Redbelly Network Terms and Conditions (Clause 15), chainlist.org, the ethereum-lists/chains repository, and vine.redbelly.network.
- Marked MOD-VERIFIED, DISCORD, NO PUBLISHED DOC: the ten-wallet activation limit, the typical KYC approval time, and the zero-balance wRBNT explainer. These came from firsthand troubleshooting and moderator confirmation in Discord rather than a published page, and are labeled as such wherever they appear.

## Design

Built to the Redbelly DAO Task Board brand kit, Kinetic Consensus: https://redbelly-dao-taskboard.vercel.app/brand

Light theme. Page background #F6F7F8, cards on white, one accent color (#B3272A for text and links, #EF5350 reserved for solid button fills only). Be Vietnam Pro for headings and body, JetBrains Mono for wallet addresses, chain IDs, and RPC URLs. No em dashes, no emoji, per the board's voice rules.

## Chain reference

| Network | Chain ID | RPC | Explorer |
|---|---|---|---|
| Mainnet | 151 | governors.mainnet.redbelly.network | redbelly.routescan.io |
| Testnet | 153 | governors.testnet.redbelly.network | redbelly.testnet.routescan.io |

Mainnet and testnet never share a field. Chain ID, RPC, and explorer are each unique to their own network.
