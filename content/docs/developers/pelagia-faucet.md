---
title: Faucet — Reef Pelagia
description: How to obtain testnet REEF for the Reef Pelagia testnet.
lead: "How to obtain testnet REEF for the Reef Pelagia testnet."
date: 2026-05-20T15:21:01
lastmod: 2026-05-20T15:21:01
draft: false
images: []
menu:
  docs:
    parent: "developers"
weight: 235
toc: true
---

# Faucet — Reef Pelagia

Reef Pelagia transactions and contract deployments are paid in REEF, the same as on the legacy network. Testnet REEF is supplied free of charge through the Pelagia web faucet.

> **Note**
> Pelagia REEF has no real value. It exists only for testing on Pelagia, cannot be bridged to mainnet, and may be wiped on chain state resets.

---

## How to request testnet REEF

The Pelagia faucet is a web application. No Discord role, no CLI, no wallet connection — just paste an address and request a drip.

1. Open the faucet at **[`https://faucet.reef-node-reefdevcluster-1e797e-72-60-35-83.nip.io/`](https://faucet.reef-node-reefdevcluster-1e797e-72-60-35-83.nip.io/)**
2. Paste the **EVM wallet address** you want funded into the address field. This is the standard `0x…` address shown by MetaMask, Trust Wallet, or Zerion when Pelagia is the selected network.
3. Click **Send drip**.
4. The faucet will queue and broadcast the funding transaction. The 2,000 REEF allocation arrives in the destination address **within 30 seconds**, often more quickly.

> **Note**
> The address must be an EVM `0x…` address. Substrate-style addresses starting with `5…` from the legacy Reef extension will be rejected.

---

## What the faucet dispenses

| Field | Value |
| --- | --- |
| Dispense amount per request | `2,000 REEF` |
| Typical delivery time | Within 30 seconds |
| Rate limit | Reasonable use; bulk requests should go through Discord |
| Requires wallet connection | No |
| Requires account or sign-in | No |

For most testing purposes, a single faucet request is enough to deploy and exercise several contracts comfortably. If your work requires substantially more testnet REEF — load testing, ecosystem partner integrations, hackathon team allocations — open a ticket in the `#dev-support` channel of the [Reef Discord](https://discord.gg/reefchain) rather than scripting against the faucet.

---

## Common issues

**The faucet page does not load.**
The endpoint is currently served on a development hostname (`*.nip.io`). If your network blocks `nip.io` by policy, you will need to access the faucet from a different connection until the production endpoint is published.

**"Invalid address" or similar error after clicking Send drip.**
Confirm you pasted a complete `0x…` EVM address — 42 characters in total, including the `0x` prefix. Common causes are a truncated paste, a leading or trailing space, or an SS58 address copied from the legacy Reef extension.

**The faucet reports success but my balance has not updated after a minute.**
Confirm your wallet is set to the **Reef Pelagia** network, not the legacy Reef mainnet or testnet. The two networks share neither state nor balances. See the [Wallet Setup Guide](#) if Pelagia is not yet configured in your wallet.

**The faucet says I have hit the rate limit.**
The rate limit is shared across requests for the same address and may also be IP-scoped. If you are working from a shared development environment, wait the cooldown period before retrying, or request a bulk allocation in `#dev-support`.

For anything else, the `#dev-support` Discord channel is monitored by the Developer Relations team during European working hours.

---

## Next steps

- [Wallet Setup Guide](/pelagia-wallet) — if you haven't yet added Pelagia to your wallet
- [Deploy Smart Contracts on Pelagia](#) — what to do with your fresh testnet REEF
- [Pelagia Testnet overview](https://docs.reef.io/docs/developers/pelagia/)