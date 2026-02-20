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
| SS58 Format     | 3939                                         |
| RPC (HTTP)      | https://rpc-pelagia.reefscan.com             |
| Block Explorer  | https://dev.papi.how/explorer#networkId=localhost&endpoint=ws%3A%2F%2F34.123.142.246%3A9944 |
```
{{< alert icon="⚠️" text="RPC endpoints above may change during early access. Always check the <a href='https://reef.io'>Reef website</a> or Discord for the latest endpoints." >}}

## Wallet Setup

<video width="50%" controls>
  <source src="https://file.notion.so/f/f/e4840ac7-ad4b-4c3c-a0d6-1ad97fc929fc/4ad26a75-c3f3-45d8-b7ad-c767b4c533e3/Kapture_2025-09-23_at_10.43.34.mp4?table=block&id=2777048b-ea54-8090-ba42-fa62f5379d94&spaceId=e4840ac7-ad4b-4c3c-a0d6-1ad97fc929fc&expirationTimestamp=1771596000000&signature=rhr5PLAqCbaiqqsJe3tgm4D2AFnVryREHrk_mmepuY8&downloadName=Kapture+2025-09-23+at+10.43.34.mp4" type="video/mp4">
</video>

To view data and block production in the console, open your browser settings and enable insecure content.

<div style="max-width: 600px; margin: 0 auto;">
  <img
    src="https://file.notion.so/f/f/e4840ac7-ad4b-4c3c-a0d6-1ad97fc929fc/117b6afe-3be0-48ab-969c-8459291615bd/Screenshot_2025-09-23_at_12.24.32.png?table=block&id=2777048b-ea54-8089-b374-dcdfef440fae&spaceId=e4840ac7-ad4b-4c3c-a0d6-1ad97fc929fc&expirationTimestamp=1771596000000&signature=x4KOcCkmmo4-svfUR4wUJ0rBwg0qjh66bn7ML800JlM&downloadName=Screenshot+2025-09-23+at+12.24.32.png"
    alt="Browser settings – enable insecure content"
    width="100%"
    style="border-radius: 8px;"
  />
</div>

## Deploy Smart Contracts

Since we are using this opportunity to upgrade Reef's Substrate/Polkadot libraries and implement `pallet-revive`,
you can begin here to find docs and tools to deploy:

[Polkadot Smart Contracts](https://docs.polkadot.com/develop/smart-contracts/)

## Next steps
Setting up your [Developer Environment](https://reefchain.notion.site/Set-Up-Your-Dev-Environment-2757048bea548090b7acd6aeb36d1d00)


Here's sample code for deploying smart contracts on Reef Pelagia testnet using Hardhat.

[Hardhat Materials](https://reefchain.notion.site/Hardhat-with-Reef-Pelagia-2757048bea5480fc9121dcc73ee74504)

If you any additional questions, please ask your questions on our [Discord Server](https://discord.gg/KAC4gSmf) and we will be happy to assist further.