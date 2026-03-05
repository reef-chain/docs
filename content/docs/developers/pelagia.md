---
title: "Pelagia Testnet"
description: "Getting started with Reef Pelagia testnet"
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

{{< alert icon="💡" text="Reef Pelagia is the brand new Reef Chain testnet, first opened to builders at Web3Conf Enugu 2025. <br>Testnet tokens have no real value and state may be reset on upgrades." >}}

## What is Pelagia?

Reef Pelagia is the new Reef Chain testnet representing the core blockchain upgrade currently
in progress. It is intended as a stress-test and feedback environment for developers before
changes are promoted to mainnet.

Pelagia was first opened to hackathon participants at
[Web3Conf Enugu 2025](https://blog.reef.io/recapping-reef-at-web3conf-enugu-2025) (September 20–27, 2025),
where multiple projects successfully deployed to it during the event.

## Network Info
```
| Key             | Value                                        |
| --------------- | -------------------------------------------- |
| Network Name    | Reef Pelagia                                 |
| Native Token    | REEF                                         |
| SS58 Format     | 13939                                         |
| RPC (HTTP)      | http://34.123.142.246:8545/                  |
| Block Explorer  | https://dev.papi.how/explorer#networkId=localhost&endpoint=ws%3A%2F%2F34.123.142.246%3A9944 |
```
{{< alert icon="⚠️" text="RPC endpoints above may change during early access. Always check the <a href='https://reef.io'>Reef website</a> or Discord for the latest endpoints." >}}

## Wallet Setup

<div style="max-width: 300px; margin: 0 auto;">
  <video width="100%" controls>
    <source src="/videos/pelagia.mp4" type="video/mp4">
  </video>
</div>


To view data and block production in the console, open your browser settings and enable insecure content.

![terminal-log](/images/pelagia/pelagia.png "")

## Deploy Smart Contracts

Since we are using this opportunity to upgrade Reef's Substrate/Polkadot libraries and implement `pallet-revive`,
you can begin here to find docs and tools to deploy:

[Polkadot Smart Contracts](https://docs.polkadot.com/develop/smart-contracts/)

## Next steps
Setting up your Developer Environment as follows:
## What to Consider

Consider the following when evaluating development environments for your workflow:
```
| Development Environment | Web-Based | Installation Required        | Best For                                   | Compilation & Deployment   | Testing & Debugging                 | Extensibility          |
| ----------------------- | --------- | ---------------------------- | ------------------------------------------ | -------------------------- | ----------------------------------- | ---------------------- |
| Remix                   | Yes       | No                           | Beginners, quick prototyping               | Built-in UI & compiler     | Basic tools                         | Limited plugin support |
| Hardhat                 | No        | Yes (via package manager)    | Advanced development, scripting, automation| Script-based               | Mocha, Chai, mainnet forking        | Highly customizable    | 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
```

If you any additional questions, please ask your questions on our [Discord Server](https://discord.gg/KAC4gSmf) and we will be happy to assist further.