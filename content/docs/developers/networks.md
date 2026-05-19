---
title: "Networks"
description: "Reef networks"
lead: "Reef's networks."
date: 2020-10-13T15:21:01+02:00
lastmod: 2026-05-18T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "developers"
weight: 230
toc: true
---

> **Building today?**
If you are starting a new project, build against **Reef Pelagia** — the current testnet on Polkadot SDK `stable2512` with the new `pallet-revive` EVM. The Legacy Reef networks below are maintained for existing deployments and will not receive new tooling support.
> 

### Reef Pelagia

Reef Pelagia is the active testnet for the next-generation Reef network. It runs on Polkadot SDK `stable2512`, executes smart contracts on PolkaVM via `pallet-revive`, and uses 12-decimal precision for the native REEF token. Pelagia is compatible with standard EVM wallets (MetaMask, Trust Wallet, Zerion, and others) through the "Add custom network" flow.

For the full overview, see the [Pelagia Testnet](https://docs.reef.io/docs/developers/pelagia/) page.

> **Note**
Pelagia testnet tokens have no real value. State may be reset on upgrades.
> 

### Pelagia info sheet

| Key | Value |
| --- | --- |
| Name, Precision | REEF, 12 |
| SS58 Format | `42` |
| EVM Chain ID | `13939` |
| Native REEF (precompile address) | `0x0000000000000000000000000000000001000000` |
| Block authoring | BABE |
| Finality | GRANDPA |
| Block time | `10s` |
| Polkadot SDK version | `stable2512` |
| Smart contract VM | PolkaVM (`pallet-revive`) |
| Code blob size limit | 100 KB |
| HTTP RPC | `https://eth.reef-node-reefdevcluster-808c46-72-60-35-83.nip.io/` |
| Faucet | See [Faucet](https://faucet.reef-node-reefdevcluster-1e797e-72-60-35-83.nip.io/) |
| Block explorer | See [Pelagia → Block explorer](https://docs.reef.io/docs/developers/pelagia/#block-explorer) |

---

## Reef mainnet
**The Legacy Reef mainnet went live on May 28th 2021.**

Legacy Reef mainnet is now considered stable, and can be used for deployment of live smart contracts.

### Legacy Reef Mainnet info sheet

```
| Key             | Value                                      |
| --------------- | ------------------------------------------ |
| Name, Precision | REEF, 18                                   |
| SS58 Format     | 42                                         |
| EVM chain id    | 13939                                      |
| REEF ERC-20     | 0x0000000000000000000000000000000001000000 |
| Block authoring | BABE                                       |
| Finality        | GRANDPA                                    |
| Block Time      | 10s                                        |
| Block Size      | 1.25MB to 3.75MB                           |
| HTTP RPC        | https://rpc.reefscan.com                   |
| Websocket       | wss://rpc.reefscan.com/ws                  |
```

## Legacy Reef testnet
Reef testnet is a common playground for deploying and testing DeFi apps. It is
recommended to first deploy apps on the testnet before launching on mainnet.

{{< alert icon="⚠️" text="Reef testnet tokens have no value and may be destroyed on testnet upgrades." >}}

### Testnet info sheet

```
| Key             | Value                                      |
| --------------- | ------------------------------------------ |
| Name, Precision | REEF, 18                                   |
| SS58 Format     | 42                                         |
| EVM chain id    | 13939                                      |
| REEF ERC-20     | 0x0000000000000000000000000000000001000000 |
| Block authoring | BABE                                       |
| Finality        | GRANDPA                                    |
| Block Time      | 10s                                        |
| Block Size      | 1.25MB to 3.75MB                           |
| HTTP RPC        | https://rpc-testnet.reefscan.com           |
| Websocket       | wss://rpc-testnet.reefscan.com/ws          |
```
