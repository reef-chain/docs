---
title: "Dokploy Instructions"
description: "Getting started with Dokploy clusters on Reef"
lead: "How to deploy clusters seamlessly using Dokploy."
date: 2026-04-23T00:00:00+00:00
lastmod: 2026-04-23T00:00:00+00:00
draft: false
images: []
menu:
  docs:
    parent: "developers"
weight: 225
toc: true
---


## Reef Cluster - Dokploy Deployment Guide

A Reef validator cluster can be deployed in **two different ways** on Dokploy:
🟢 **[Method 1: Single Template (Full Cluster Setup)](#-method-1-single-template---full-cluster-setup)** [RECOMMENDED]
- A single deployment handles bootnode + all validators + RPC.

🔵 **[Method 2: Multiple Templates (Bootstrap + Individual Validators)](#-method-2-multiple-templates---bootstrap--validators)**
- You deploy bootstrap + validators separately for more control.
---
# 📑 **Table of Contents**

- [📑 **Table of Contents**](#-table-of-contents)
    - [🟢 **Method 1: Single Template – Full Cluster Setup**](#-method-1-single-template--full-cluster-setup)
    - [🔵 **Method 2: Multiple Templates – Bootstrap \& Validators**](#-method-2-multiple-templates--bootstrap--validators)
    - [Deploy 2 or more validators → finalize blocks.](#deploy-2-or-more-validators--finalize-blocks)
    - [Local Docker deployment instructions:](#local-docker-deployment-instructions)


---

### 🟢 **Method 1: Single Template – Full Cluster Setup**

<a id="step-1-generate-validator-keys"></a>

**Step 1: Generate Validator Keys**


1. Go to **Create Service**

   <img src="https://github.com/user-attachments/assets/61ffc1b3-7601-4fa0-a8c9-37dd91fe5f0c" alt="Create Service" style="max-width: 600px; width: 100%; height: auto;">

2. Select **Template** from the menu.

3. Add template repo URL at the top-right:


4. Search for **"Reef"**

<img src="https://github.com/user-attachments/assets/0a73fe6e-7e5d-4553-bcd7-0dca6fc2a831" alt="Search Reef" style="max-width: 600px; width: 100%; height: auto;">

5. Click **Create** on **Reef Chain – Keys Generator**, then confirm.

<img src="https://github.com/user-attachments/assets/2a8cae47-6ad4-4d82-aa79-3f7dfb9599ff" alt="Keys Generator Create" style="max-width: 600px; width: 100%; height: auto;">

6. Deploy the service.

<img src="https://github.com/user-attachments/assets/82aa445a-c1b7-46de-aa20-abbecc5b79ba" alt="Deploy Service" style="max-width: 600px; width: 100%; height: auto;">

7. Visit the port `http://reef.host:48765` or your IP address / hostname at port `48765`

<img src="https://github.com/user-attachments/assets/6566a708-3d07-4c90-8dba-26a123dc8514" alt="Visit Port 48765" style="max-width: 600px; width: 100%; height: auto;">

8. Copy all **address + seed pairs**, they will be needed later.

<img src="https://github.com/user-attachments/assets/1efb99f2-aa24-4ff4-8326-da8a79104afd" alt="Copy Address Seed Pairs" style="max-width: 600px; width: 100%; height: auto;">


---
 **Step 2: Deploy Custom Spec Generator**

1. Go to Templates and search for:


**Reef Chain – Custom Spec Generator**

<img src="https://github.com/user-attachments/assets/990a8521-7a7e-43ae-aaa1-72b1ac253a13" alt="Custom Spec Generator" style="max-width: 600px; width: 100%; height: auto;">

2. Deploy it.

3. It runs on port **8000** by default:

<img src="https://github.com/user-attachments/assets/6d6a5b02-8c8b-4926-a635-a6829c2c2c4d" alt="ETH RPC Running" style="max-width: 600px; width: 100%; height: auto;">
<img src="https://github.com/user-attachments/assets/3d66ed43-4e6c-48c5-953a-ca12cfede6db" alt="ETH RPC Dashboard" style="max-width: 600px; width: 100%; height: auto;">


🎉 **Your full cluster (bootnode + validators + RPC + ETH RPC) is now live.**


---
### 🔵 **Method 2: Multiple Templates – Bootstrap & Validators**

**Step 1: Generate Validator Keys (Same as Method 1)**

👉 Jump to: [Generate Validator Keys](#step-1-generate-validator-keys)

**Step 2: Deploy Bootnode Validator**

Create service → choose template:

**Reef Chain – Bootnode Validator**

<img src="https://github.com/user-attachments/assets/dd42462e-22c9-44f9-8625-01cad45a77d6" alt="Bootnode Validator Template" style="max-width: 600px; width: 100%; height: auto;">

Fill in:

* `v1sec`, `v2sec`, `v3sec`
* `v1addr`, `v2addr`, `v3addr`
* `PORT=8000` → exposes custom spec
* `P2P_PORT=30335` → bootnode peer port

<img src="https://github.com/user-attachments/assets/eb2a26a8-bc5c-4d54-aade-b47086c9fd89" alt="Bootnode Environment Config" style="max-width: 600px; width: 100%; height: auto;">

Bootnode starts → no peers yet (expected behavior).


---
**Step 3: Deploy Additional Validators**

Use:
**Reef Chain – Validator**

<img src="https://github.com/user-attachments/assets/98c57f34-d1f6-48e4-a11b-09a514817e0f" alt="Validator Template" style="max-width: 600px; width: 100%; height: auto;">

##### Deploy 2 or more validators → finalize blocks.
---
**Deploy ETH RPC (Method 2)**

Same template:

 **Reef Chain – ETH RPC**

<img src="https://github.com/user-attachments/assets/e3644fdf-4465-4fc8-967b-10f9d93513bc" alt="ETH RPC Template" style="max-width: 600px; width: 100%; height: auto;">

> ⚠️ **Important** — ETH RPC default port: `http://reef.host:8545`
---------
#### Local Docker deployment instructions:
1. clone the git repo.
   
   `git clone -b reef-chain https://github.com/anukulpandey/dokploy-templates.git`
2. switch to the reef-dev-cluster directory.
   
   `cd dokploy-templates/blueprints/reef-dev-cluster`
3. Start the docker instance:
   
   `docker-compose up`
4. Verify the logs — once completed, your logs should look similar to the following:
````
reef-dev-cluster-1  | 2026-04-23 09:41:22 Running JSON-RPC server: addr=127.0.0.1:42967,[::1]:36105
reef-dev-cluster-1  | 2026-04-23 09:41:22 〽️ Prometheus exporter started at 127.0.0.1:9618
reef-dev-cluster-1  | 2026-04-23 09:41:22 👶 Starting BABE Authorship worker
Container reef-dev-cluster-reef-dev-cluster-1 Healthy
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 🌐 Connecting to node at: ws://reef-dev-cluster:9945 ...
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 🌟 Connected to node at: ws://reef-dev-cluster:9945
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 💾 Using in-memory database, keeping only 256 blocks in memory
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 Node does not have getAutomine RPC. Defaulting to automine=false.
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 〽️ Prometheus exporter started at 127.0.0.1:9616
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 Running JSON-RPC server: addr=0.0.0.0:8545,[::]:32917
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 🔌 Subscribing to new blocks (BestBlocks)
reef-dev-cluster-eth-rpc-1  | 2026-04-23 09:41:26 🔌 Subscribing to new blocks (FinalizedBlocks)
reef-dev-cluster-1          | ==> /tmp/bootnode.log <==
reef-dev-cluster-1          | 2026-04-23 09:41:27 💤 Idle (0 peers), best: #0 (0xe72c…1267), finalized #0 (0xe72c…1267), ⬇ 0 ⬆ 0
````
---------
