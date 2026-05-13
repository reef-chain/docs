---
title: "Pelagia Testnet"
description: "Connect to and deploy on Reef Pelagia, the next-generation Reef testnet."
lead: "Learn how to connect to and deploy on Reef Pelagia, the next-generation Reef Chain testnet."
date: 2026-02-20T00:00:00+00:00
lastmod: 2026-02-20T00:00:00+00:00
draft: false
images: []
menu:
  docs:
    parent: "developers"
weight: 225
toc: true
---

Reef Pelagia is the testnet for the next-generation Reef network. It introduces a new EVM implementation built on `pallet-revive`, runs on Polkadot SDK `stable2512`, reduces the native REEF token to 12 decimal precision, and — for the first time — is compatible with standard EVM wallets including MetaMask, Trust Wallet, and Zerion via "Add custom network" flows.

> **Note**
Pelagia is a testnet. Tokens have no real value, and network state may be reset between upgrades. Do not use mainnet keys or hold anything of value on Pelagia.
>

## What is changing on Pelagia

For developers familiar with the legacy Reef network, Pelagia is a substantial change rather than an incremental upgrade. The core differences are:

- **New runtime stack.** Pelagia is built on Polkadot SDK `stable2512`, replacing the five-year-old runtime that previous Reef networks were based on.
- **New EVM implementation.** Smart contracts now execute on PolkaVM via `pallet-revive`, rather than on the legacy `pallet-evm`. Solidity 0.8.0 and above is supported; contracts are compiled with the `resolc` compiler.
- **12-decimal native token.** REEF now has 12 decimals of precision on Pelagia, down from 18 on the legacy network. Every application that handles REEF amounts as raw wei needs to account for this change. See the [Migration Guide](https://claude.ai/chat/6e45a2ec-7c76-43a4-85eb-2e454693bd1e#) for details.
- **Standard EVM wallet support.** Adding Pelagia as a custom network in MetaMask, Trust Wallet, Zerion, Rabby, or any other EVM-compatible wallet is now sufficient to view balances, sign transactions, and interact with contracts. The Reef browser extension is no longer required.
- **Larger contract size limit.** PolkaVM raises the contract code blob limit to 100 KB, compared with Ethereum's 24 KB.

Pelagia was first opened to hackathon participants at [Web3Conf Enugu 2025](https://blog.reef.io/recapping-reef-at-web3conf-enugu-2025) (September 20–27, 2025), where multiple projects deployed during the event.

---

## Network parameters

The values below are everything required to connect a wallet, an RPC client, or any standard EVM tooling to Pelagia.

| Parameter | Value |
| --- | --- |
| Network name | Reef Pelagia |
| Native token symbol | REEF |
| Native token decimals | 12 |
| EVM Chain ID | `13939`  <sub>// confirm with chain team</sub> |
| SS58 prefix | `42`  <sub>// confirm with chain team</sub> |
| HTTP RPC | `https://rpc-pelagia.reef.io`  <sub>// placeholder; current endpoint is `http://34.123.142.246:8545/`</sub> |
| WebSocket RPC | `wss://rpc-pelagia.reef.io/ws`  <sub>// placeholder</sub> |
| Block explorer | See [Block explorer](#block-explorer) below |
| Polkadot SDK version | `stable2512` |
| Smart contract VM | PolkaVM (`pallet-revive`) |
| Solidity support | `0.8.0` and above, compiled via [`resolc`](https://github.com/paritytech/revive) |
| Contract code blob limit | 100 KB |

> **Note**
RPC endpoints may change during early access. The values above are the source of truth; always cross-check on the [Reef website](https://reef.io/) or in [Discord](https://discord.gg/KAC4gSmf) before scripting against them.
> 

---

## Add Pelagia to your wallet

Pelagia works with any wallet that supports adding a custom EVM network. The most common setups are:

- **MetaMask** — paste the values from the table above into *Settings → Networks → Add a network manually*.
- **Trust Wallet** — *Settings → Networks → Add custom network*.
- **Zerion** — *Settings → Networks → Add custom network*.
- **Rabby** — *Settings → Networks → Add custom network*.

For step-by-step instructions with screenshots, see the full [Wallet Setup Guide](https://#).

> **Note**
The legacy Reef browser extension is not required to interact with Pelagia. Existing users can continue to use it for the legacy network; for Pelagia, any standard EVM wallet will work.
> 

---

## Get testnet REEF

Smart contract deployment and transactions on Pelagia require REEF to cover gas. Testnet REEF is available free of charge from the faucet.

Full instructions, rate limits, and the current dispense amount are documented on the [Faucet](https://#) page.

---

## Deploy a smart contract

Pelagia accepts standard Solidity contracts, but they must be compiled to PolkaVM bytecode using `resolc` rather than `solc` directly. The supported workflow is via the `@parity/hardhat-polkadot` Hardhat plugin.

The shortest path:

```bash
mkdir my-pelagia-project && cd my-pelagia-project
npm init -y
npm install --save-dev @parity/hardhat-polkadot@0.1.9
npx hardhat-polkadot init
npm install
```

Add a network entry for Pelagia to `hardhat.config.js`:

```jsx
require('@nomicfoundation/hardhat-toolbox');
require('@parity/hardhat-polkadot');
const { vars } = require('hardhat/config');

module.exports = {
  solidity: '0.8.28',
  resolc: { compilerSource: 'npm' },
  networks: {
    hardhat: { polkavm: true },
    reefPelagiaTestnet: {
      polkavm: true,
      url: 'http://eth.reef-node-reefdevcluster-808c46-72-60-35-83.sslip.io',
      accounts: [vars.get('PRIVATE_KEY')],
    },
  },
};
```

Set your deployer key and deploy:

```bash
npx hardhat vars set PRIVATE_KEY "INSERT_PRIVATE_KEY"
npx hardhat compile
npx hardhat ignition deploy ./ignition/modules/MyToken.js --network reefPelagiaTestnet
```

For the full walkthrough — including the compilation flow, local testing, and worked deployment examples — see [Deploy Smart Contracts on Pelagia](https://#) and the [Hardhat Materials](https://docs.reef.io/docs/developers/hardhat/) page.

---

## Block explorer

A Pelagia-aware build of [Blockscout](http://explorer-frontend-y3vx1v-aaa30a-72-60-35-83.sslip.io/) is availablein progress. Other explorer options include:

- **Polkadot.js Apps**, pointed at the Pelagia WebSocket endpoint, for inspecting blocks, extrinsics, and Substrate-level state.
- **Standard JSON-RPC tooling** (`eth_getTransactionByHash`, `eth_getBlockByNumber`, etc.) against the Pelagia HTTP RPC.

Contract source verification on Pelagia is supported via the verifier endpoint described on the [Hardhat Materials](https://docs.reef.io/docs/developers/hardhat/) page.

---

## Tooling compatibility

The table below summarises which developer tools are known to work against Pelagia, which are confirmed incompatible, and which are still under evaluation.

| Tool | Pelagia support | Notes |
| --- | --- | --- |
| MetaMask | ✅ | Add as custom network |
| Trust Wallet | ✅ | Add as custom network |
| Zerion | ✅ | Add as custom network |
| Hardhat (`@parity/hardhat-polkadot`) | ✅ | Required plugin; see [Hardhat Materials](https://docs.reef.io/docs/developers/hardhat/) |
| Remix | ✅ | Via Polkadot Remix plugin |
| `ethers.js` (v6) | ✅ | Against the HTTP RPC |
| `viem` | ✅ | Against the HTTP RPC |
| `web3.js` | ⚠️ | Works for most reads; some helpers untested |
| Foundry | ⚠️ | Under evaluation |
| Hardhat Network helpers (`time`, `loadFixture`) | ❌ | Not supported by `pallet-revive` |
| The Graph (subgraphs) | ⚠️ | Pending hosted service evaluation |
| `@reef-defi/evm-provider` (legacy) | ❌ | Legacy network only |
| Reef browser extension (legacy) | ❌ | Legacy network only — use MetaMask on Pelagia |

---

## Next steps

- [**Wallet Setup Guide**](https://#) — step-by-step instructions for MetaMask, Trust Wallet, and Zerion
- [**Faucet**](https://#) — how to obtain testnet REEF
- [**Deploy Smart Contracts on Pelagia**](https://#) — full Hardhat walkthrough
- [**Migration Guide**](https://#) — for developers moving from the legacy Reef network
- [**Hardhat Materials**](https://docs.reef.io/docs/developers/hardhat/) — full Hardhat reference, including local testing and the `resolc` compiler
- [**FAQ and Troubleshooting**](https://#) — common Pelagia issues and resolutions

For questions not covered in the documentation, the [Reef Discord](https://discord.gg/KAC4gSmf) is the fastest path to a Developer Relations response.