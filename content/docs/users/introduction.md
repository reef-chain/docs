---
title: "Introduction"
description: "Reef Chain is a fast, affordable EVM-compatible chain for DeFi. You can use this guide to learn how to write and deploy Solidity smart contracts."
lead: "Reef Chain is an EVM-compatible chain for building fast, easy-to-use products with NPoS consensus."
date: 2020-10-06T08:48:57+00:00
lastmod: 2025-10-23T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "users"
weight: 100
toc: true
---


## Get started

If you're looking for things you can do with Reef, check out the [Reef Ecosystem](/docs/users/ecosystem) and [AwesomeReef](https://awesomereef.xyz).

### Build on Reef

Get started with Reef by installing the [Reef node](/docs/developers/nodes/), and deploying a simple DeFi app locally in [Quick Start]({{< ref "quick-start" >}}).

For in depth tutorials on the underlying aspects of the Reef chain check out the [Developer Guide]({{< ref "quick-start" >}}) and the [Developer Resources]({{< ref "resources" >}}).

### Governance

[Validators](/docs/governance/validators/) and [Nominators](/docs/governance/nominators/) are essential to the Reef ecosystem.

Learn how to [stake](/docs/governance/staking/) your Reef tokens and vote for validators. Highly technical users may also participate in validator elections to have a chance of becoming a paid block producer.


## Why Reef?
Reef is fast, scalable, has low transaction costs and features easy-to-use core apps.

Reef chain features next-gen blockchain technology, utilizing Nominated Proof of Stake, extensible EVM, on-chain upgradability, libp2p networking and state of the art cryptography.

### Fees
Reef is efficient, and has a predictable algorithmic fee model. All fees from Reef chain usage are
automatically burned.
```
| Cost of:                    | Ethereum   | Reef       |
| --------------------------- | ---------- | ---------- |
| Making a payment            | $1         | $0.05      |
| Executing an Uniswap trade  | $1         | $0.12      |
| Deploying an ERC-20 Token   | $5+        | $1.95      |
| Minting a NFT               | $5+        | $2.16      |
```
*\*Last updated on Oct 23rd 2025*


#### Reef vs legacy chains
|                             | Bitcoin             | Ethereum            | Reef                           |
| --------------------------- | ------------------- | ------------------- | ------------------------------ |
| Consensus algorithm         | Proof of Waste      | Proof of Stakes      | Nominated Proof of Stake       |
| Energy consumption          | More than [Poland](https://digiconomist.net/bitcoin-energy-consumption)    | Same as [Gibraltar](https://digiconomist.net/ethereum-energy-consumption)   | Less than a shopping mall |
| On-Chain upgradability      | N/A                 | N/A                 | Yes                            |
| Transaction finality        | 3600+ seconds       | 600+ seconds        | 40 seconds                     |
| Block time                  | ~600 seconds        | ~17 seconds         | 10 seconds                     |
| Max block size              | < 2MB               | N/A                 | 3.75MB                         |
| Throughput                  | 7 tps               | 14 tps              | [465](/blog/reef-testnet-stress-test/) tps  |
| Smart contracts             | No                  | Yes, EVM            | Yes, EVM                       |
