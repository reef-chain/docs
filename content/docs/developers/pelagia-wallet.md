---
title: "Wallet Setup — Reef Pelagia"
description: "Add the Reef Pelagia testnet to MetaMask, Trust Wallet, Zerion, and other EVM wallets."
lead: "Add the Reef Pelagia testnet to MetaMask, Trust Wallet, Zerion, and other EVM wallets."
date: 2026-02-20T00:00:00+00:00
lastmod: 2026-02-20T00:00:00+00:00
draft: false
images: []
menu:
  docs:
    parent: "pelagia"
weight: 225
toc: true
---

Reef Pelagia is the first Reef network compatible with standard EVM wallets. This guide covers adding Pelagia as a custom network in the three most commonly requested wallets: MetaMask, Trust Wallet, and Zerion. The same parameters work in Rabby, OKX Wallet, Coinbase Wallet, and any other wallet that supports user-defined networks.

> **Note**
Pelagia is a testnet. Use a fresh wallet or a dedicated testnet account; never import a mainnet seed phrase containing real assets into a wallet you will use against an experimental network.
> 

---

## The parameters you will need

Before opening any wallet, have these values ready. They are the only values required to add Pelagia to a custom-network wallet:

| Field | Value |
| --- | --- |
| Network name | `Reef Pelagia` |
| RPC URL | `http://eth.reef-node-reefdevcluster-808c46-72-60-35-83.sslip.io` |
| Chain ID | `13939` |
| Currency symbol | `REEF` |
| Block explorer URL | `http://explorer-frontend-y3vx1v-aaa30a-72-60-35-83.sslip.io/` |

All other parameters (decimals, SS58 prefix, WebSocket URL, etc.) are handled by the wallet automatically once these values are in place.

---

## MetaMask (browser extension and mobile)

The flow is identical on the browser extension and on the mobile app, with minor differences in where each menu lives.

### Browser extension

1. Open MetaMask and click the **network selector** in the top-left of the extension popup.
2. Click **Add a custom network**. *(In older versions: Settings → Networks → Add a network → Add a network manually.)*
3. Fill in the form with the parameters from the table above.
4. Click **Save**.
5. MetaMask will switch to Reef Pelagia automatically. You should see `0 REEF` as your balance until you fund the account from the [faucet](https://#).

> *Screenshot placeholder: MetaMask "Add a custom network" form with Pelagia values filled in.*
> 

### Mobile

1. Tap the hamburger menu → **Settings** → **Networks** → **Add network**.
2. Switch to the **Custom Networks** tab.
3. Fill in the same five fields and tap **Add**.

---

## Trust Wallet (mobile)

1. Open Trust Wallet and tap the **Settings** tab at the bottom of the screen.
2. Tap **Networks** → **Add custom network**.
3. Fill in the form with the parameters from the table above. The "Symbol" field corresponds to "Currency symbol."
4. Tap **Save**.
5. Return to the wallet home screen and use the network switcher (top of the screen) to select **Reef Pelagia**.

> *Screenshot placeholder: Trust Wallet "Add custom network" screen with Pelagia values.*
> 

> **Note**
Trust Wallet sometimes hides custom networks behind the "Manage" toggle on the asset list. If REEF does not appear after adding the network, tap **Manage** on the asset list and enable it.
> 

---

## Zerion (mobile and web)

### Mobile

1. Open Zerion and tap the **Settings** tab.
2. Tap **Networks** → **Add custom network**.
3. Enter the parameters from the table above.
4. Tap **Add Network**.

### Web

1. Open `app.zerion.io` and connect your wallet.
2. Click your profile in the top-right → **Settings** → **Networks**.
3. Click **Add custom network**.
4. Enter the parameters from the table above and click **Save**.

> *Screenshot placeholder: Zerion "Add custom network" form with Pelagia values.*
> 

---

## Other wallets

The same five fields work in:

- **Rabby** — *Settings → More → Custom RPC → Add*
- **OKX Wallet** — *Settings → Networks → Custom network*
- **Coinbase Wallet** — *Settings → Networks → Add custom network*
- **Frame** — *Settings → Chains → Add new chain*

If your wallet supports EIP-3085 (`wallet_addEthereumChain`), Pelagia can also be added with a single click via a dApp that calls the standard request. A one-click "Add Pelagia" button is available on the [testnet web app](http://reef-node-reefapp-kcriyx-a2707a-72-60-35-83.sslip.io/).

---

## Verifying the connection

Once the network is added and selected:

1. Your wallet should display a `0 REEF` balance.
2. The network indicator in the wallet UI should read `Reef Pelagia`.
3. If you have funded the address from the faucet, the balance should update within the next block (~6–12 seconds).

If the wallet shows a connection error or the network selector hangs, see the [FAQ and Troubleshooting](https://#) page.

---

## Funding your wallet

A freshly added Pelagia account holds zero REEF. To deploy contracts or send transactions, request testnet REEF from the [faucet](http://faucet.reef-node-reefdevcluster-1e797e-72-60-35-83.sslip.io).

---

## What if I already use the Reef browser extension?

The Reef browser extension was the standard way to interact with the legacy Reef network. It is still supported for legacy mainnet and legacy testnet, but on Pelagia it is no longer required. You can:

- Continue using the Reef extension for the legacy network, and
- Use MetaMask (or any other EVM wallet) for Pelagia in parallel.

Most browsers happily run both extensions side by side. The accounts are entirely separate; nothing migrates automatically. The full implications are covered in the [Migration Guide](https://#).

---

## Next steps

- [Get testnet REEF from the faucet](https://#)
- [Deploy your first contract on Pelagia](https://#)
- [FAQ and Troubleshooting](https://#)